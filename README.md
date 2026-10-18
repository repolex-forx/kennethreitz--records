# Repolex Knowledge Graph of kennethreitz/records

RDF knowledge graph data for [kennethreitz/records](https://github.com/kennethreitz/records), parsed by [repolex](https://repolex.ai).

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
rlex download kennethreitz/records
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── ea4273695cee6da42edf1cb294d1f2a4505470fc
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── ea4273695cee6da42edf1cb294d1f2a4505470fc
│           └── chunk-001.nq.gz
├── blob
│   ├── 034bf266f057804a270e58bfa3f8d8d8e9f01953.nq.gz
│   ├── 086803092d54ef831751da2b3211e8d9482dcb0d.nq.gz
│   ├── 1b907d32be951fbbaf781ef1936c27a8f1dc6e80.nq.gz
│   ├── 4c49bd78f1d08f2bc09fa0bd8191ed38b7dce5e3.nq.gz
│   ├── 4e63b6b6203a854d8073aa2bc84880cc5632c7ec.nq.gz
│   ├── 4e93a8b39c407ef3d0d8afe8305f4e570f4738a9.nq.gz
│   ├── 677cf347aceec41f428de48b086531550991be1b.nq.gz
│   ├── 6c6aca5a706975455ef67f87bd896eed7924ab8a.nq.gz
│   ├── 6df6b369fa95801ae9277b6a670f570cfa2dc9c1.nq.gz
│   ├── 72b1a4f282a7cec50ba54086c1788d608cb985a9.nq.gz
│   ├── 89c00d40ce681cc09eec90a3d1aea39bbec1344c.nq.gz
│   ├── 9dfdf39d0b4c5d98c5ce1493a2780720793a3c7f.nq.gz
│   ├── b5b6766347e48939802f48cc0532b7d648251ae8.nq.gz
│   ├── b694f92f1d4d21132a5ffb09aaeaf2fdc02440dc.nq.gz
│   ├── b9655b507468457a83859bc2121343a5ccbe975c.nq.gz
│   ├── c2395bb743f2bd0ac931f6269749595e8c43fc43.nq.gz
│   ├── c9255b33213fdad986f3d31ab9d3beffbc3b95d7.nq.gz
│   ├── d43e89e84237b99da4fa9028c9c43fe63c14329d.nq.gz
│   ├── ddfee8ed16f7df2d9b7e666312bd1b2e6e62c9f9.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── f8e6406f6b47a8be2f9c17e08a32071b057a0791.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── ea4273695cee6da42edf1cb294d1f2a4505470fc.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 29 files
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

[kennethreitz/records](https://github.com/kennethreitz/records)

---
*Parsed on 2026-10-18 by [repolex](https://repolex.ai)*
