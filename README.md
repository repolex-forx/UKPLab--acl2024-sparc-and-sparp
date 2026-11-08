# Repolex Knowledge Graph of UKPLab/acl2024-sparc-and-sparp

RDF knowledge graph data for [UKPLab/acl2024-sparc-and-sparp](https://github.com/UKPLab/acl2024-sparc-and-sparp), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [rlex](https://github.com/repolex-ai/rlex) query tool:

```bash
cargo install --git https://github.com/repolex-ai/rlex
```

Verify the install:

```bash
rlex --help
```

**rlex is designed to be used primarily by LLMs in a terminal.** Start up your favorite AI assistant and ask it to use rlex. It handles the SPARQL — you just ask questions in plain English.

To load this repo's data:

```bash
rlex download UKPLab/acl2024-sparc-and-sparp
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── b4568a8030976941cb0037fb6399d48f893d8fa4
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── b4568a8030976941cb0037fb6399d48f893d8fa4
│           └── chunk-001.nq.gz
├── blob
│   ├── 0a7cce335fe0972f6a82681eb76b3714c46f8a02.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 284ae9b02fa9d90e5d66b055d697ccd3d1fe62bb.nq.gz
│   ├── 2c96babefc95cb947c92a8fb5097d2ee3e69a9c3.nq.gz
│   ├── 2e846fa8ae9ff3756de10a0a717c472c0ce5e9b7.nq.gz
│   ├── 33a064288c9276640f59cfd54ca19470f547f727.nq.gz
│   ├── 3602769adf5cda0a5bde4d2d4434358d040bea1d.nq.gz
│   ├── 40f6e47428cadefa18cee31958e0bc35a19d4067.nq.gz
│   ├── 4238654bfb226b3b77d332522bad6e755dcfddeb.nq.gz
│   ├── 47818bb4ef15ca8b5dd00f3e54573022f4e17e9c.nq.gz
│   ├── 4ea5168e21815a1e7fef656ed5d06afe84e450d7.nq.gz
│   ├── 529a8d6e644af2db98305a7cab72b5e20abf5ee5.nq.gz
│   ├── 81de13ee680496a039b0fabf2a770799abff6c5a.nq.gz
│   ├── 82d2a4cc5460c96b23e150c5f00df0db56f4be41.nq.gz
│   ├── 8d1994349b6ed17f1580041fad5f1dee7d7edeac.nq.gz
│   ├── 8f9a4a208e1f6a0f3a1df651c09ffce7e364c522.nq.gz
│   ├── a2f79bb138cf29c8f8209f235bd9e1d7afb56b07.nq.gz
│   ├── a55eff4940f608ffc4ab3ca15148ee75bb2bc1fc.nq.gz
│   ├── ac4c82aa0c9b22e620ddf236a30447821a7a10cd.nq.gz
│   ├── aee27055b7a1bb72627586c59661253c1bf95721.nq.gz
│   ├── b499e6416e88bea8f6598dec6e96a10a7555563d.nq.gz
│   ├── b697f62112270e406dade20b0480d079d1012d68.nq.gz
│   ├── b9d7668703dc88959405f3c545d1eaa9e244e0f7.nq.gz
│   ├── bfdbda6eea92131541f6edc706e4ea246cc409e0.nq.gz
│   ├── c7ee717b7bebf3782017592ba1dd69607cadb7b2.nq.gz
│   ├── c947dc4e6e88f82caf67262b8b82bb020097a4ca.nq.gz
│   ├── ca21844d69758fbb0d17fa8e45be814ca16049a7.nq.gz
│   ├── cea6098edc5afedd5a488ef0f60f11338223773f.nq.gz
│   ├── d60b99fc62bf3e49c530274240eec65204a24540.nq.gz
│   ├── db288d308f136db3c237c1d0cf84ab96a6d4b3b8.nq.gz
│   ├── e5ad4f9c0f8eab55095c9e79ef6e50d4f941b74d.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── ea469b0a7fbecde203464c603ac150c1baee7423.nq.gz
│   ├── ecf419694a2b1d1879c6c7b30572fa09efc0bcf7.nq.gz
│   ├── ed76b596ea088aa0fe4db07f593f97b6b0808c1d.nq.gz
│   ├── f183d3d07255ca46e292030a13bb11c93061ea63.nq.gz
│   └── fbefb6f5ac38664c5d8ef7be284b02a60e3e1ba4.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── b4568a8030976941cb0037fb6399d48f893d8fa4.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 43 files
```

| Directory | What it contains |
|-----------|-----------------|
| `blob/` | Per-file AST graphs, content-addressed by git blob SHA. Each file in the source repo gets its own graph. |
| `aggregate/ast/` | Combined AST graph per parsed commit. Merges all blob graphs for a snapshot of the entire codebase at that point. |
| `aggregate/lsp/` | Language Server Protocol enrichment: resolved symbols, definitions, references, and type information. |
| `aggregate/dataflow/` | Interprocedural data flow edges between functions and modules. |
| `aggregate/repolex/` | Combined graph (AST + LSP + dataflow) per commit. |
| `commit/` | Git commit metadata (author, date, message, parent links). |
| `branch/` | Branch metadata. |
| `tag/` | Tag metadata. |
| `filetree/` | File tree snapshots per commit (which files existed and their blob SHAs). |
| `audit/` | Code architecture and graph audit reports per commit. |

## Source repository

[UKPLab/acl2024-sparc-and-sparp](https://github.com/UKPLab/acl2024-sparc-and-sparp)

---
*Parsed on 2026-11-08 by [repolex](https://repolex.ai)*
