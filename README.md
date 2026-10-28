# Repolex Knowledge Graph of databrickslabs/dolly

RDF knowledge graph data for [databrickslabs/dolly](https://github.com/databrickslabs/dolly), parsed by [repolex](https://repolex.ai).

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
rlex download databrickslabs/dolly
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── e2d664ddf06e0723d818dc56d6c522ead4bd881d
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── e2d664ddf06e0723d818dc56d6c522ead4bd881d
│           └── chunk-001.nq.gz
├── blob
│   ├── 03d1df2b2a9dfc56bb7e5ce6593f0dc3c33ba88f.nq.gz
│   ├── 03d973e0b71a011dbdba759d6b877181331674f2.nq.gz
│   ├── 13624c8a9e139760b6e18a44acfe2dfbfa7fb713.nq.gz
│   ├── 14cfd56bca9dee610810ff242420adc1e96a4f58.nq.gz
│   ├── 1d844e08d20c148082e75bfcf181e48eeb671ffd.nq.gz
│   ├── 2fb704efabc9f6fc91ab134407d59244e8f8ff66.nq.gz
│   ├── 306a8d9ca038c15b347b1bbb2e88ca8bbeb11b82.nq.gz
│   ├── 3aab9f088e9948e5408ac74ca75643d46a53bcf2.nq.gz
│   ├── 6ede3536c33e69cb10d639a21543cc6d23adaf27.nq.gz
│   ├── 7394c5d87eac391c8ec621048d22fe6fd6171c02.nq.gz
│   ├── 7b545debc229aea1d50ee43323d267173cf7a73f.nq.gz
│   ├── 7d2b6d0b0cd27da5db4b81781dd8ff1e5bc44888.nq.gz
│   ├── 853ed47e1a229fe2d6c56c33411fb06030442f94.nq.gz
│   ├── c23bb0816a4a9710344fe9fb7a4d4197c962144e.nq.gz
│   ├── d1aabcbbd3de8162ba5b42290878eb813a5d25a5.nq.gz
│   ├── d9e6004dc051dd395b913048dd1a4835a11e8eaf.nq.gz
│   ├── dc094f7046bf28fa3c9eb5445735b1a99403b3bb.nq.gz
│   ├── dfb619dd53d25b12f461407bdecfc79d242dae3e.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── f4f5d33e986bbc6db77cdca048bebad7d9bab2cf.nq.gz
│   ├── f90b9ee601593e11c7964e484367c9dcc267243a.nq.gz
│   ├── fca72582149c1aff8e10a2c7896b60e5e51a0075.nq.gz
│   └── fefae5e195c6e9c088c17c1efb9de4805338ee90.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── e2d664ddf06e0723d818dc56d6c522ead4bd881d.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 31 files
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

[databrickslabs/dolly](https://github.com/databrickslabs/dolly)

---
*Parsed on 2026-10-28 by [repolex](https://repolex.ai)*
