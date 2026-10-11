# Repolex Knowledge Graph of samuelcolvin/cloudkv

RDF knowledge graph data for [samuelcolvin/cloudkv](https://github.com/samuelcolvin/cloudkv), parsed by [repolex](https://repolex.ai).

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
rlex download samuelcolvin/cloudkv
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── c5cb4dec9fe6cdc7e186a148065aa17fa3e08ca0
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── c5cb4dec9fe6cdc7e186a148065aa17fa3e08ca0
│           └── chunk-001.nq.gz
├── blob
│   ├── 04066374dc55baa7b6c33ec6bf960f860f21160d.nq.gz
│   ├── 083387a404cb987329e0c6e68f8d71701192af1e.nq.gz
│   ├── 0c7bd1daadc32f8d7f830d8c2c343409fe210da3.nq.gz
│   ├── 0cf98ca2c3c3e2b3a0bd0595872333937b08e044.nq.gz
│   ├── 1a09f443f6af369185ad7d78c38d883594bf0b1b.nq.gz
│   ├── 1a5f4c28ff5f909ded60492e24dcda845d93c1c8.nq.gz
│   ├── 220b17d73a76cec0bd724fb8b11964d88a933cb1.nq.gz
│   ├── 23ab4b8fc8dd1ea1bd912d7a4d3211bdc7a209be.nq.gz
│   ├── 24ee5b1be9961e38a503c8e764b7385dbb6ba124.nq.gz
│   ├── 2a3a336dd6ba63c2a9fdca34cd32aa6274d6395d.nq.gz
│   ├── 2f1db52c430386ffe837aaacd92e72dc38eab67b.nq.gz
│   ├── 4654c5f7d07833e314f10694606329f1ec366980.nq.gz
│   ├── 46f8e3723a901123c102bf29029889dc76b7c2a9.nq.gz
│   ├── 66590715e02b1fed821b796aaca27d68c404b887.nq.gz
│   ├── 8dbae5e198096bc3bed2d8704871512deb5f09b4.nq.gz
│   ├── 95290f35880ec276ae0aa44624ea59d482297435.nq.gz
│   ├── 95e001f041518ffc1c1fa88f59590d0ae3a9ee60.nq.gz
│   ├── 96c543c4408ba7e898bf38cb6b47a8ddec72234b.nq.gz
│   ├── 97599fea644c7e3ac3faf06303d403d6794d59c2.nq.gz
│   ├── 9a3b10f6cdc8458412fe58efcf1150fd4e02cd5f.nq.gz
│   ├── aaf5a407c5f141d34cc6a57d0481d7fc85451350.nq.gz
│   ├── acf3933e9f17430dc5cd2314b10c8c0ea514c3bf.nq.gz
│   ├── b100d71dcd5ea5be3d0c7aee7561f3d8c5b29b36.nq.gz
│   ├── b75a0fa9c318bbfd66c39a80e455cddeb394a520.nq.gz
│   ├── bb0a4703852ef3d86051a0e215d22af46f6db39d.nq.gz
│   ├── bb18ac4af8a572f9a9c8af73983385001e0d6e07.nq.gz
│   ├── c8cd0f4be29a337bd0f90f4bec18c194127d4336.nq.gz
│   ├── d593e436f88c30d7a3b648e94c1ad594f29b4922.nq.gz
│   ├── d7c285504e84ba0097ff06d53e4914b64570843b.nq.gz
│   ├── d89aabef9de7298fef67d91062b8738afc2152d6.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── fdaa1090ec6e59760306274e43eec2a202c0bfd1.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── c5cb4dec9fe6cdc7e186a148065aa17fa3e08ca0.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 39 files
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

[samuelcolvin/cloudkv](https://github.com/samuelcolvin/cloudkv)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
