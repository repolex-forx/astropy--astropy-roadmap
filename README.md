# Repolex Knowledge Graph of astropy/astropy-roadmap

RDF knowledge graph data for [astropy/astropy-roadmap](https://github.com/astropy/astropy-roadmap), parsed by [repolex](https://repolex.ai).

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
rlex download astropy/astropy-roadmap
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── a529bb2dfc94e16592c51e23b20bc18a72b93f63
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── a529bb2dfc94e16592c51e23b20bc18a72b93f63
│           └── chunk-001.nq.gz
├── blob
│   ├── 06950bb06321cdee8960f7661ed1a17ee6a876de.nq.gz
│   ├── 128048c640862bc92e86354bbcbef39069cc8640.nq.gz
│   ├── 2359e691cbd9dc9ae4592a1b36483cf97ed031bf.nq.gz
│   ├── 2ede6e9b719496f7cbd17338437f90d410dcd3b3.nq.gz
│   ├── 33065e35d24089dcf2f96b58080de3519bb1c1bd.nq.gz
│   ├── 343d25256eb4b0eeffd6b9b9b67538cc6663b102.nq.gz
│   ├── 41c3f6ee05498dd5513e941c1b7b81c7ef715525.nq.gz
│   ├── 66003ee5feff4a66c8cf621c33854e62f8c3e6b5.nq.gz
│   ├── 6a3467216f2f10436aef13de7fda3651bfe8d4c5.nq.gz
│   ├── 7f58085350eb8bfea8edf6bb4e101aeca2fc7101.nq.gz
│   ├── 89531d2a76ae528bf4d25c45b1393a3e797fa428.nq.gz
│   ├── 950f0bba66aae75b89fbe08607f819631b45e5f7.nq.gz
│   ├── ac7c683e74ca3a6dd1ccfbb044d238a55c07fcd6.nq.gz
│   ├── bf1cb55bc05830f10cb9a6469bc1dfd53a90253c.nq.gz
│   ├── c2cd7f703635788b35fd6ec9b2889a0417f46f06.nq.gz
│   ├── ca6423f37284cf0475f13697e6f30f132400854a.nq.gz
│   └── d4bfa1e18252f81dc872add1d3a7f7dc6d001ddc.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── a529bb2dfc94e16592c51e23b20bc18a72b93f63.nq.gz
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

[astropy/astropy-roadmap](https://github.com/astropy/astropy-roadmap)

---
*Parsed on 2026-11-07 by [repolex](https://repolex.ai)*
