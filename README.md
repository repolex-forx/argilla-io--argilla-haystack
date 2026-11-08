# Repolex Knowledge Graph of argilla-io/argilla-haystack

RDF knowledge graph data for [argilla-io/argilla-haystack](https://github.com/argilla-io/argilla-haystack), parsed by [repolex](https://repolex.ai).

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
rlex download argilla-io/argilla-haystack
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 358f42948799a072c8b846abb369e2c39bbff3e0
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 358f42948799a072c8b846abb369e2c39bbff3e0
│           └── chunk-001.nq.gz
├── blob
│   ├── 138ab145596e6c06d5f3ea9bdbbfed0babe0835e.nq.gz
│   ├── 1e211c56686fb85e845840148cdc883b9dde89c7.nq.gz
│   ├── 3264c89f86e705e6de9861b8f2025f860757f504.nq.gz
│   ├── 417e287b1278851210e85752f14f39b435e295b9.nq.gz
│   ├── 458e8d1b4b485f90f413d880645df2d992140ddb.nq.gz
│   ├── 58aeda7b9caf0b2675250d2fbd4d276139fa492a.nq.gz
│   ├── 68bc17f9ff2104a9d7b6777058bb4c343ca72609.nq.gz
│   ├── 743350d443b858ac2c711bffb0ee5bbb557018dd.nq.gz
│   ├── 7455fe861cd18a530a33f29bf40ad790be4b272f.nq.gz
│   ├── 7ceb52df6e29bdfab395b7065a0d74e72e3df633.nq.gz
│   ├── 810dc3b22545e10db755885bed5ddbe8e19c20c6.nq.gz
│   ├── 8d5d539df63d77175824dadbc542a3e8e59a72cf.nq.gz
│   ├── a3526620ca8c57dbad945ecf4942a9677729af5b.nq.gz
│   ├── b1b7dd03d8a9a52bf20536c0e21ea83a0f2dac68.nq.gz
│   ├── b6d7fb1a0f9d2c92da7d40a1ed0d5e6796d2a881.nq.gz
│   ├── c61bfee7b0dee8ffab3022fb96fd00b5da44fa80.nq.gz
│   └── fb9c662fe364e4105926502847444e982875e3dc.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 358f42948799a072c8b846abb369e2c39bbff3e0.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 25 files
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

[argilla-io/argilla-haystack](https://github.com/argilla-io/argilla-haystack)

---
*Parsed on 2026-11-08 by [repolex](https://repolex.ai)*
