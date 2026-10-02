# Repolex Knowledge Graph of NousResearch/hermes-plugin-snyk

RDF knowledge graph data for [NousResearch/hermes-plugin-snyk](https://github.com/NousResearch/hermes-plugin-snyk), parsed by [repolex](https://repolex.ai).

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
rlex download NousResearch/hermes-plugin-snyk
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 2a41a07f81e45125bf82a19af1b13396ace4b81f
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 2a41a07f81e45125bf82a19af1b13396ace4b81f.nq.gz
│   └── repolex
│       └── 2a41a07f81e45125bf82a19af1b13396ace4b81f
│           └── chunk-001.nq.gz
├── blob
│   ├── 04e2c83c95630a5925666e499d5eae2c7e1c93ea.nq.gz
│   ├── 2b9e73b53f01cb2a635d6910c99925fb3a8d5532.nq.gz
│   ├── 5cd142e64e1f96da97bd3d44d1bb91c428372271.nq.gz
│   ├── 64777da0fbb4b64e1c9bd2c05af650b9d8497a17.nq.gz
│   ├── 75410e73319c72cd3e991a501c5455eb78f38375.nq.gz
│   ├── a1bd7784c437a8adc9427637298714a3261ad6c2.nq.gz
│   └── b083f68e41cca04440eae83df5b36b1753e30951.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 2a41a07f81e45125bf82a19af1b13396ace4b81f.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 14 files
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

[NousResearch/hermes-plugin-snyk](https://github.com/NousResearch/hermes-plugin-snyk)

---
*Parsed on 2026-10-02 by [repolex](https://repolex.ai)*
