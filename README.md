# Repolex Knowledge Graph of simonw/datasette-publish-fly

RDF knowledge graph data for [simonw/datasette-publish-fly](https://github.com/simonw/datasette-publish-fly), parsed by [repolex](https://repolex.ai).

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
rlex download simonw/datasette-publish-fly
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── a14b34ade8965ffeb2afc25026ce77bd9b76f640
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── a14b34ade8965ffeb2afc25026ce77bd9b76f640
│           └── chunk-001.nq.gz
├── blob
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 33f396efcca3b5c76555cbbd0eafa5dae2b77356.nq.gz
│   ├── 40961eb85ef9df8b3619b4e7cfe526f66081309f.nq.gz
│   ├── 6b2715e7ece586afca8b27baf09d8ed126ee1938.nq.gz
│   ├── 78cabc80b1db702e841e4107dffaa9197022c96a.nq.gz
│   ├── 7ab76d14788e9fd85f40b20f65e18f04666bab29.nq.gz
│   ├── 89354c88f9521f2823867cdb4e445bec1eed2a51.nq.gz
│   ├── b1423a6ba88ca59ce6804883ae5261bc138bb743.nq.gz
│   ├── bd4edd67feacc64a89d5d32067e6824cd775dd29.nq.gz
│   ├── bef16d0d8bd01031e377a5dc2b0f2c8b5bdb9347.nq.gz
│   ├── c7085eb761e592c4cba32297fa8af34f0a203ed4.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── f7e055382c4fbbac81d2dfd8b065e53044b9aa7a.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── a14b34ade8965ffeb2afc25026ce77bd9b76f640.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 21 files
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

[simonw/datasette-publish-fly](https://github.com/simonw/datasette-publish-fly)

---
*Parsed on 2026-10-12 by [repolex](https://repolex.ai)*
