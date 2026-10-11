# Repolex Knowledge Graph of tiangolo/node-frontend

RDF knowledge graph data for [tiangolo/node-frontend](https://github.com/tiangolo/node-frontend), parsed by [repolex](https://repolex.ai).

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
rlex download tiangolo/node-frontend
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 58105139a4b8877f96bbbc2409354e697191f539
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 58105139a4b8877f96bbbc2409354e697191f539
│           └── chunk-001.nq.gz
├── blob
│   ├── 0ffc101a3f23548392499fe5104f3f8cf4d4e91b.nq.gz
│   ├── 1536d81f15d0d1950d8c737355396efff000f52b.nq.gz
│   ├── 5b3973300bbd906da44fc0ef689fdbce75585d56.nq.gz
│   ├── 77e557a5b044a8a132dccea12b4a8e27435cbb15.nq.gz
│   ├── a96f24ab43e3132e81ed551bd3dcf8dfb01efc02.nq.gz
│   ├── ad46b30886fa350c1f59761b100e5e4b01f9a7ec.nq.gz
│   ├── ba4d9aad6cab8a7af73af6aae9f22d6cf8b79835.nq.gz
│   ├── f38bbf487994a413b2787f88f7848abbc12c08ca.nq.gz
│   ├── f5e54526dea3885cdf826cc022131568c3b00634.nq.gz
│   ├── f6e68136ef7a3eb215cb295cf2c74160ba3150b1.nq.gz
│   └── f93fa1c1661768899c6f2f5d4a614c0c7e1e8345.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 58105139a4b8877f96bbbc2409354e697191f539.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 19 files
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

[tiangolo/node-frontend](https://github.com/tiangolo/node-frontend)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
