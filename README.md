# Repolex Knowledge Graph of sphinx-contrib/requirements

RDF knowledge graph data for [sphinx-contrib/requirements](https://github.com/sphinx-contrib/requirements), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/requirements
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 70906a63d314512c4807a4fbbe944e4396411e0d
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 70906a63d314512c4807a4fbbe944e4396411e0d
│           └── chunk-001.nq.gz
├── blob
│   ├── 2d74c58f248790e34e482eb07e20ec6c753c9d2d.nq.gz
│   ├── 392d9544cffbecdb48da5e22e4c179bf2f9e9287.nq.gz
│   ├── 5391d87392a9983b4dcac6751022ac8b0c20e424.nq.gz
│   ├── 627ea8b1b031872719f3bba3d47c26c8b3d2b16c.nq.gz
│   ├── 79ed66fbd7fd315515140f238cb68cabcdeddfee.nq.gz
│   ├── 8175cb8c93e15baeabc8d9feb171d0f4d1c6275f.nq.gz
│   ├── 8e7e2bc0d26ebc39199523caf9850ff62f3d650a.nq.gz
│   ├── b4898d482dfeb569675a50752c41dc4a25be4073.nq.gz
│   ├── b5a7dc29ef0f7f3593b1c61cfc5dfe8a17d3918c.nq.gz
│   └── df15ed18b61da6ebc94d3c052f5acb1217305bb7.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 70906a63d314512c4807a4fbbe944e4396411e0d.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 18 files
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

[sphinx-contrib/requirements](https://github.com/sphinx-contrib/requirements)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
