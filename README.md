# Repolex Knowledge Graph of klen/pypika-orm

RDF knowledge graph data for [klen/pypika-orm](https://github.com/klen/pypika-orm), parsed by [repolex](https://repolex.ai).

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
rlex download klen/pypika-orm
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 2a07539ce2c792581f8b600458de1a42520621c0
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 2a07539ce2c792581f8b600458de1a42520621c0
│           └── chunk-001.nq.gz
├── blob
│   ├── 00db7efa5eeb7f16101aa4e6863a7f1bf998fdf1.nq.gz
│   ├── 04ac6fccc17fe4cc9dc04fa1f564d009f1448b7a.nq.gz
│   ├── 09f2cb071516ebbedcc0a232ac215601e6d2db45.nq.gz
│   ├── 16a513f9928df3d3dc0f185736c89275ad0c8e0c.nq.gz
│   ├── 255e8c2a6b4bc50d2a8caf4caf5efa996d99c0f9.nq.gz
│   ├── 29b115733f4f8911f9cb2224332386a00a501c3d.nq.gz
│   ├── 5d325b9eee0101facc2bd425e9c15306bac0a630.nq.gz
│   ├── 5e66eb8f1c38aa21a540d9efaf9bb8b46b74a961.nq.gz
│   ├── 64866748c9e9b7c8a0746dc622e821ede92103fe.nq.gz
│   ├── 6fb6d1da6a78077176220691528cadc3feff3c4a.nq.gz
│   ├── 9999ce0c86c84a767a1e8ee65e20291107da8746.nq.gz
│   ├── a64f24433d07673ac4a41f46ef0dbc6fae452f28.nq.gz
│   ├── a99d1c67137c60261e4f9758efa5196f13c60227.nq.gz
│   ├── b1c4a2641a58a5822113e7b0382e5e3ec31bc5ac.nq.gz
│   ├── b49e36794573339ef756340a1ae4afc9920782b7.nq.gz
│   ├── b79c31480eeaed1cbb95006040a59ba26bb8a1bb.nq.gz
│   ├── bf726d0a1f52070f6b8be0b86d07295ad26a1547.nq.gz
│   ├── c99d4ff46656f8087b0967b3a02d4ad614435b69.nq.gz
│   ├── d0a3c3d449f96ac8144d9bd7c85ec6c15b2b76b4.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── fc71a33421b81a939533cbdc026a90b7c70b7365.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 2a07539ce2c792581f8b600458de1a42520621c0.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 27 files
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

[klen/pypika-orm](https://github.com/klen/pypika-orm)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
