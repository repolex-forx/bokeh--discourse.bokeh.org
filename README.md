# Repolex Knowledge Graph of bokeh/discourse.bokeh.org

RDF knowledge graph data for [bokeh/discourse.bokeh.org](https://github.com/bokeh/discourse.bokeh.org), parsed by [repolex](https://repolex.ai).

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
rlex download bokeh/discourse.bokeh.org
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── c88b5cf476053bb8086fdbff3afb8003d2c5a838
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── c88b5cf476053bb8086fdbff3afb8003d2c5a838
│           └── chunk-001.nq.gz
├── blob
│   ├── 0c5f86896e07a6ad4e20f241fbe7a6b4e37f0672.nq.gz
│   ├── 0f4c9da10e3aa2c67ec3c014593e9b379078c680.nq.gz
│   ├── 30ff2999ccf1498152ebac867a5b9c1b35c7da81.nq.gz
│   ├── 3127db3c24f5cb053ebb3f3f9b5f82f30f2efc15.nq.gz
│   ├── 31426abf2c2c1b909f5479ffd3a1380d3824e587.nq.gz
│   ├── 345319e926ebdeb97c07e58038e9ab5fed5fef63.nq.gz
│   ├── 36cf73753a0e1a49888d4250150727fec9286a57.nq.gz
│   ├── 39cb91f7a0da4625bd68eeca5d972a5859d098fe.nq.gz
│   ├── 4146e67cf1cb1bd38a4dbdfa81d3d4fdb1107c23.nq.gz
│   ├── 4a0c04d75c38e9e7500722ac531cd3bb0971a1bb.nq.gz
│   ├── 594d1df33e81c5af3edb21e28e33d083a347f705.nq.gz
│   ├── 6d92148b550efd40d63c4f42810105b1d5df95ad.nq.gz
│   ├── 7d81e9cb1bfb804eb8bc83ada7bf0784c6a09004.nq.gz
│   ├── 7ffaba2296f500bd3e16604d05f3214aec2c4f4d.nq.gz
│   ├── 82776be37777092ea5c59e1c2fb2679c269b97a3.nq.gz
│   ├── 9cb5c84e45c53709946f8e9a29bca2a6f36f9380.nq.gz
│   ├── a870607515386ab0edef98ab9b0d45f7c52e284c.nq.gz
│   ├── c384bea2bff883e9f29dc504a9a4bdbe09f1c099.nq.gz
│   ├── ed79226178f59aff1f7dd6f4cd094e01ede55349.nq.gz
│   └── f3beffacea58bc0e219ed3b03f468382429eb031.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── c88b5cf476053bb8086fdbff3afb8003d2c5a838.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 26 files
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

[bokeh/discourse.bokeh.org](https://github.com/bokeh/discourse.bokeh.org)

---
*Parsed on 2026-11-08 by [repolex](https://repolex.ai)*
