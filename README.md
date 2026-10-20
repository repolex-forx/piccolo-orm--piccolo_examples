# Repolex Knowledge Graph of piccolo-orm/piccolo_examples

RDF knowledge graph data for [piccolo-orm/piccolo_examples](https://github.com/piccolo-orm/piccolo_examples), parsed by [repolex](https://repolex.ai).

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
rlex download piccolo-orm/piccolo_examples
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── f4d636dada433257b9fc8b4b72c2fb0ed88ec0ee
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── f4d636dada433257b9fc8b4b72c2fb0ed88ec0ee
│           └── chunk-001.nq.gz
├── blob
│   ├── 01bae3ea0c91a46c06be25be2847ad357bd5e9b3.nq.gz
│   ├── 1ed445c7916e4df36b4b2882debd00638e3ff45d.nq.gz
│   ├── 22df358be9ce2bde62d3e6a61dc519e3721786ff.nq.gz
│   ├── 3a575c2063c5bb7c1b0baf2cf2f852b83c2345d8.nq.gz
│   ├── 65d6ab4d0582530f40331271714a355ad3df2498.nq.gz
│   ├── 66f48bad1a3da7c16eebcda2f4be36cb0029cc9c.nq.gz
│   ├── 8d1cbe75fd43fa87b885c858cc4e22b9b9608ea5.nq.gz
│   ├── a9577373683a126d10530ec77781af532aa70aba.nq.gz
│   ├── ace7c58328a690321e6a3a6a00d5c3779d5674b4.nq.gz
│   ├── dd640d030a727ee827d3e2f0a68e59b50fe63a8e.nq.gz
│   ├── dde43411f706206f010f909a6182e5af2a15db03.nq.gz
│   ├── eed5a4109fad0c47be902357ec52f0704f4bb486.nq.gz
│   └── f76a1d217246a8d30a5389a8d7e5db249cc80406.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── f4d636dada433257b9fc8b4b72c2fb0ed88ec0ee.nq.gz
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

[piccolo-orm/piccolo_examples](https://github.com/piccolo-orm/piccolo_examples)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
