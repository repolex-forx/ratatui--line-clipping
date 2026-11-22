# Repolex Knowledge Graph of ratatui/line-clipping

RDF knowledge graph data for [ratatui/line-clipping](https://github.com/ratatui/line-clipping), parsed by [repolex](https://repolex.ai).

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
rlex download ratatui/line-clipping
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── d734cc5c1a2e6f9d60eeda996650cefa193be719
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── d734cc5c1a2e6f9d60eeda996650cefa193be719.nq.gz
│   └── repolex
│       └── d734cc5c1a2e6f9d60eeda996650cefa193be719
│           └── chunk-001.nq.gz
├── blob
│   ├── 0dfc8dca2211858d1d5d089f4990403b07f6a84f.nq.gz
│   ├── 220d5846c99103a4e5ac6ba034367828893184ad.nq.gz
│   ├── 33844523a014926cdcce056e7a50cbb5120a0919.nq.gz
│   ├── 3b5a5d0d2365019bc70c078cd579fa2d5c9ef892.nq.gz
│   ├── 849a0ca79279ab4159166ae63ae4469299529aa4.nq.gz
│   ├── 94206f8fe954509d4fe67c38c70fdf784916cf76.nq.gz
│   ├── 94a0c784e9155a9197223189611e7aa594678f21.nq.gz
│   ├── 96ae3828c1352b2c650259068782f1e82b7c19df.nq.gz
│   ├── 9dd7a63238625664f50db1a618ede17dbbc377b8.nq.gz
│   ├── a16cd4a545b8ae5e1d7d40a859a434e87d020d54.nq.gz
│   ├── a4e8b4b6bbc3107e40ccaf5540868fd573b9e9e4.nq.gz
│   ├── b4d4df5244bb95f163c178074fbda16c03ce3680.nq.gz
│   ├── b508b22521c56bfb6ab4658a643810b1143c0f2a.nq.gz
│   ├── e4c0503bfdd62235428db26944510547ddb5f657.nq.gz
│   ├── ea8c4bf7f35f6f77f75d92ad8ce8349f6e81ddba.nq.gz
│   └── eca00ad91b5cea06914e8db3ea00664b007cbfa8.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── d734cc5c1a2e6f9d60eeda996650cefa193be719.nq.gz
├── filetree
│   └── d734cc5c1a2e6f9d60eeda996650cefa193be719.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

14 directories, 25 files
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

[ratatui/line-clipping](https://github.com/ratatui/line-clipping)

---
*Parsed on 2026-11-22 by [repolex](https://repolex.ai)*
