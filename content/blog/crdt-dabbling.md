---
title: "Dabbling in CRDTs"
date: 2026-11-16
tags:
  - crdt
  - automerge
  - yjs
  - loro
  - distributed-systems
  - kotlin
---

<video autoplay loop muted playsinline controls style="width: 100%">
  <source src="../assets/crdt.webm" type="video/webm">
</video>

Recently was trying out CRDTs (Conflict-free Replicated Data Types🤓) to write my own little apps and mostly for my own amusement. In my opinion this is one of the best use cases for local-first, offline-first or close-proximity connectivity apps out there.

This data structure lets multiple clients edit offline and merge their changes consistently (eventually!) without a central server or merge conflicts, the files are just blobs and all the changes are available for review, just like in #git.

Among those amazing projects are [Automerge](https://github.com/automerge/), [Loro](https://loro.dev/) and [Yjs](https://github.com/yjs/yjs).

Especially interesting is their Movable Tree implementation, described in great detail here https://loro.dev/blog/movable-tree - allows to work with tree implementations where hierarchy matters and not to get crazy.

In the example above I am trying out an app written in #kotlin with [Lexical](https://lexical.dev/) editor that syncs CRDT changes from the very same folder.

Lexical runs in an embedded WebView bridge, emitting change deltas to Loro on the Kotlin side 🔻

---

A few notes on how it's wired together under the hood. The main idea is keeping the CRDT tree 100% pure (0 bytes of crypto metadata inside Loro) and handling all encryption as an envelope at the I/O level.

### 1. Loro Rust (UniFFI)

UniFFI procedural macros annotate the Rust struct and methods so the code generator can produce the Kotlin/Swift bindings:

```rust
// 1. Generates foreign language scaffolding
uniffi::setup_scaffolding!();

// 2. Marks the Rust struct as an exported foreign object
#[derive(uniffi::Object)]
pub struct LoroDoc {
    doc: InnerLoroDoc,
}

// 3. Exposes constructors and methods to Kotlin / Swift
#[uniffi::export]
impl LoroDoc {
    #[uniffi::constructor]
    pub fn new() -> Arc<Self> {
        Arc::new(Self { doc: InnerLoroDoc::new() })
    }

    pub fn export_updates(&self, vv: &VersionVector) -> Vec<u8> {
        self.doc.export_from(&vv.into())
    }

    pub fn import(&self, bytes: &[u8]) -> Result<(), LoroError> {
        self.doc.import_with(bytes)?;
        Ok(())
    }
}
```

---

### 2. Kotlin Multiplatform (CRDT Mutate & Export)
Kotlin interacts with the UniFFI bridge directly:

```kotlin
// Peer A: Mutate text container and block tree
val docA = LoroDoc()

// 1. Plain text edit
val text = docA.getText("page_body")
text.insert(0, "Offline edit from Desktop A")

// 2. Block-based hierarchy (Movable Tree)
val tree = docA.getTree("page_blocks")
val headerNode = tree.createNode(targetParentId = null, index = 0)
val paragraphNode = tree.createNode(targetParentId = headerNode, index = 0)

// Move node safely: Loro guarantees cycle-free moves across peers!
tree.move(paragraphNode, targetParentId = null, toIndex = 1)

// 3. Export delta since last known frontier/version vector
val deltaBytes: ByteArray = docA.exportUpdates(lastVersionVector)
```

---

### 3. Envelope Encryption (AES-256-GCM)
The CRDT tree remains 100% pure (0 bytes of crypto metadata inside Loro). Sealing happens at the I/O boundary:

```kotlin
val aad = "$realmId:$documentId".encodeToByteArray()
val rmk = getRealmMasterKey() // 32-byte symmetric AES key

// --- Peer A: Seal before dropping onto the shared folder ---
val encryptedBatch = cipher.encrypt(
    key = rmk,
    plaintext = deltaBytes,
    associatedData = aad
)

// --- Peer B: Read from sync folder -> Decrypt in memory -> Merge ---
val docB = LoroDoc()
val cleartextDelta = cipher.decrypt(rmk, encryptedBatch, aad)

// Deterministic convergence: Fugue merges text, Movable Tree resolves hierarchy
docB.import(cleartextDelta)
```

