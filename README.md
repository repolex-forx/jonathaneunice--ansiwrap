# Repolex Knowledge Graph of jonathaneunice/ansiwrap

RDF knowledge graph data for [jonathaneunice/ansiwrap](https://github.com/jonathaneunice/ansiwrap), parsed by [repolex](https://repolex.ai).

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
rlex download jonathaneunice/ansiwrap
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── a20c337ceec328792ce41866ca2cb6099a618bea
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── a20c337ceec328792ce41866ca2cb6099a618bea
│           └── chunk-001.nq.gz
├── blob
│   ├── 0a07d7be9d8ba4e8d5725c82147fbc2e5cc36672.nq.gz
│   ├── 1e81e88cfd3c169450c954f8a0bc2b7f03144cac.nq.gz
│   ├── 27a54479051e7b69ea26989e979f9a694d8d1709.nq.gz
│   ├── 3165c82065556780c25d339cd099f0d62161afd8.nq.gz
│   ├── 352d7330784e3d67a6b1a782c97620e056249017.nq.gz
│   ├── 3bacb7ef9e732dc73cfd210907cd51fe9fe4bcd6.nq.gz
│   ├── 43de87d41857d83f6fdbc291b3b2e91fd3019a84.nq.gz
│   ├── 4d1fa36c36d984bf0043f235a4de705308202d23.nq.gz
│   ├── 56b47d1702268fb3e6862cc3ed1cf704313b0d40.nq.gz
│   ├── 57cde3b0370037e0dc005a14cb60e497d864c842.nq.gz
│   ├── 6138caaeffe8dd3f9cc7f84aa3c3517ba0dd39b2.nq.gz
│   ├── 6a18dc6fc58011d766e2b4c0b2c131a4b7a00400.nq.gz
│   ├── 6cd2a98bf7b3401ab6773580e5541efba327b2f8.nq.gz
│   ├── 6e1c2017a4cbde8c8e814b111be0a53e48830472.nq.gz
│   ├── 75a6bdb5a22b8312c6b8b6e206765cadcf117f93.nq.gz
│   ├── a5a5daf4c333b62e77acf9c2652df4a3dc8943e6.nq.gz
│   ├── ae53f350b0123e8638b37e100c21a1fd2aa19b7c.nq.gz
│   ├── bb9c4c063afb4f6b1a9d5f77126daabee71cca78.nq.gz
│   ├── c03c801d0c4e2623371a8b24ff7f854813c3ca98.nq.gz
│   ├── cf6ceec77ce88bd43bebe3c4f7fa31cfb5db3aa3.nq.gz
│   ├── d648c2f399ef78bcf5478fec6f23946433b7c6ff.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── eb9b5501d8445d1268ca96cc60bb67322e0d0dc4.nq.gz
│   └── fad0e0d48a90f098af4927d8c592f2737a9430ff.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── a20c337ceec328792ce41866ca2cb6099a618bea.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 32 files
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

[jonathaneunice/ansiwrap](https://github.com/jonathaneunice/ansiwrap)

---
*Parsed on 2026-10-18 by [repolex](https://repolex.ai)*
