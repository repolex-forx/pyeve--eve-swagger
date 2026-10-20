# Repolex Knowledge Graph of pyeve/eve-swagger

RDF knowledge graph data for [pyeve/eve-swagger](https://github.com/pyeve/eve-swagger), parsed by [repolex](https://repolex.ai).

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
rlex download pyeve/eve-swagger
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── d28f917706fedc055b171bfedea60a681a62b224
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── d28f917706fedc055b171bfedea60a681a62b224
│           └── chunk-001.nq.gz
├── blob
│   ├── 180e699dec1f23648878b43e4f7e0c7a2d030968.nq.gz
│   ├── 4c2eb4aa02de6acc05e11b4624cd38476bcb544b.nq.gz
│   ├── 538d81c58cb9c0131315f35fd64adc0fbd7eb7a9.nq.gz
│   ├── 539b9b4c876b62611e022ebe4e89f4afe9606a75.nq.gz
│   ├── 5e441e14ed5789d8069a8bf5ce34a2879f9730a9.nq.gz
│   ├── 6dc101f4917a126b649fb7d0d63e657c483509ba.nq.gz
│   ├── 774a6ac1c9c5cf0153928627bc4d4b281c3ed697.nq.gz
│   ├── 7806c1c00594a3c15814e990555536592bc665ad.nq.gz
│   ├── 7908e7afab5d1ab8e55b62623c55ff0cfb1db225.nq.gz
│   ├── 7a20521c9fb922e51a65eb7b64f690dee5f65b89.nq.gz
│   ├── 7ceec44424f531103da51c8d8424f4bb85af6d6b.nq.gz
│   ├── 7f4a7f25747ae4ed7053abea6164577d98b6b18f.nq.gz
│   ├── 90f6f63a93689002f8e1e005aa40a90d7d607093.nq.gz
│   ├── 9358e0c6897274c53cc98621b7ed405acfe366b2.nq.gz
│   ├── 9b3904f4c14991ce289cac5a5869edfde95c4f55.nq.gz
│   ├── 9fbad1da032bc172ea079306421facbbbf2afff5.nq.gz
│   ├── a6f2ae0da4fce820f64ea8ecdd73f84657aea7c1.nq.gz
│   ├── a85215ce7a363590520d2ac2caad117988d612cc.nq.gz
│   ├── a87d12bcd6189c3fa2c22bf6c493477b1cac8be3.nq.gz
│   ├── ac19726fff2958e48e517839c4fc762a9537c1ac.nq.gz
│   ├── b62381728f4d78c5848dd0c002809fbf6fe0ff70.nq.gz
│   ├── ea894bb87055cad6c4c2a9f6c3868531d3017506.nq.gz
│   ├── f3a338e1ce92c4c86112593acd72215904d3552f.nq.gz
│   ├── f49ccb5d37bbe2ba1029ea36c2bf0f2dc6d3a7e9.nq.gz
│   └── f74801a1f3e15a264dc5fa6a5b5d7b1488adc8ca.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── d28f917706fedc055b171bfedea60a681a62b224.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 33 files
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

[pyeve/eve-swagger](https://github.com/pyeve/eve-swagger)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
