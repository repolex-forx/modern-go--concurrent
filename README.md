# Repolex Knowledge Graph of modern-go/concurrent

RDF knowledge graph data for [modern-go/concurrent](https://github.com/modern-go/concurrent), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [lexq](https://github.com/repolex-ai/lexq) query tool using [uv](https://docs.astral.sh/uv/getting-started/installation/).

If you have uv installed, just copy/paste this into your terminal:

```bash
uv tool install git+https://github.com/repolex-ai/lexq
```

This installs lexq onto your system, in your user context. Verify the install:

```bash
lexq --help
```

**lexq is designed to be used primarily by LLMs in a terminal.** Start up your favorite LLM and ask it to use the lexq tool. It's that easy!

To load this repo's data:

```bash
lexq download modern-go/concurrent
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── bacd9c7ef1dd9b15be4a9909b8ac7a4e313eec94
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── bacd9c7ef1dd9b15be4a9909b8ac7a4e313eec94.nq.gz
│   └── repolex
│       └── bacd9c7ef1dd9b15be4a9909b8ac7a4e313eec94
│           └── chunk-001.nq.gz
├── blob
│   ├── 05a77dceb1e23e95882e18ed707fb682fbdeec44.nq.gz
│   ├── 16ba3e5f7d48f875135998d2cc7f8a743c6c3439.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 3f2bc47416e77ca0771c85d681d782d2201096ae.nq.gz
│   ├── 449e67cd01acba105df358ccac3c32f0693f3f1a.nq.gz
│   ├── 623dba1ac00f22d1becb9e67e8a26a5b20bc2799.nq.gz
│   ├── 9756fcc75a79cb0af9b4049ed5543a3496d2b3a6.nq.gz
│   ├── acab3200aa2e470c2bdd35ccfd9b9111f7c978e9.nq.gz
│   ├── aeabf8c4f9c808648014f38bbb7919ab31b25e72.nq.gz
│   ├── b9c8df7f4101b6270690d9f6526c6e2466109d78.nq.gz
│   ├── d1e6b2ec554450c3565764a8238b54ee9dcd7776.nq.gz
│   └── fe86e84a39c8ff9a9dbbbd89e434b27d325f6735.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── bacd9c7ef1dd9b15be4a9909b8ac7a4e313eec94.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

14 directories, 21 files
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

## Source repository

[modern-go/concurrent](https://github.com/modern-go/concurrent)

---
*Parsed on 2026-09-16 by [repolex](https://repolex.ai)*
