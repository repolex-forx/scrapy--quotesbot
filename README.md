# Repolex Knowledge Graph of scrapy/quotesbot

RDF knowledge graph data for [scrapy/quotesbot](https://github.com/scrapy/quotesbot), parsed by [repolex](https://repolex.ai).

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
rlex download scrapy/quotesbot
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 16ec3f4176db67ca9132f7e4431d7823e5e28974
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 16ec3f4176db67ca9132f7e4431d7823e5e28974
│           └── chunk-001.nq.gz
├── blob
│   ├── 250b253917aa6e7b892f8b2b5ef40720c3fe01a0.nq.gz
│   ├── 2aff2d76ba60e71b0b4f006e955991239bacb4a8.nq.gz
│   ├── 555e2040d76f207c3dca0752441b16fa732fb3b8.nq.gz
│   ├── 63a00a96f4825212da516cc5ef8afdf985f3ca19.nq.gz
│   ├── 692bb0121b8de7aa134bb5f6ea15f9dcb21ec54a.nq.gz
│   ├── 72364f99fe4bf8d5262df3b19b33102aeaa791e5.nq.gz
│   ├── 9599fd8069d36fa9268c08cbdd00199a415a51f1.nq.gz
│   ├── b9c5e70e31f8f5c216acba35cd39c54817e43ebe.nq.gz
│   ├── c33bc3fe72f38e47d076a8e1330dcda087a15a1f.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── ebd689ac51d69c5e1dbbe80083c2b20a39f8bb79.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 16ec3f4176db67ca9132f7e4431d7823e5e28974.nq.gz
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

[scrapy/quotesbot](https://github.com/scrapy/quotesbot)

---
*Parsed on 2026-10-12 by [repolex](https://repolex.ai)*
