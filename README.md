# Repolex Knowledge Graph of huggingface/ipyh-optimization

RDF knowledge graph data for [huggingface/ipyh-optimization](https://github.com/huggingface/ipyh-optimization), parsed by [repolex](https://repolex.ai).

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
rlex download huggingface/ipyh-optimization
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 029fbbf6e5f8b5a3e6ba2a22874d7264a18956e5
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 029fbbf6e5f8b5a3e6ba2a22874d7264a18956e5
│           └── chunk-001.nq.gz
├── blob
│   ├── 145e7243883be0311a0905a6f82f54c14efaea3e.nq.gz
│   ├── 163a215516bc87c5037a4f3c970dc9b23b1beeb7.nq.gz
│   ├── 1d238ec26d28c186f54356408d59145ef13958ef.nq.gz
│   ├── 26ef0f4ae5f269b6435a13a42c8b76634a8aafd6.nq.gz
│   ├── 29c4cd9857f2882bbb274379d699d5372122697f.nq.gz
│   ├── 2d67ce5cdee000ba6eea4c71df8047302f165e96.nq.gz
│   ├── 34ca9d170a488d3c9d3b8836f0b7ead57e741878.nq.gz
│   ├── 36acd53a599a3840b266d8aaee14258f479fd750.nq.gz
│   ├── 3e95b719050df0be96da5d3a8bc40c769328777b.nq.gz
│   ├── 3fdca0126d88a48dd1d6c0ddaa2dff808a1af1ff.nq.gz
│   ├── 5875a21cd28150a94e12fbf97080d8758e5ebf12.nq.gz
│   ├── 5a3bbe4f765cf1e390b8ad1f935d3635c4311658.nq.gz
│   ├── 83e6e3ded75a23211d45824e3cd82eeff297ef60.nq.gz
│   ├── 8504ab24222a2d420b999eebc849131270ad2829.nq.gz
│   ├── 99aacc5db9e196be3a1cbc823c4075fc4172191b.nq.gz
│   ├── ac8c593fbfd3855d336c10ff74b2dacd14f093a2.nq.gz
│   ├── c077e128228385f09fdda0d0484dc482ba58d485.nq.gz
│   ├── c0c39bb04aadcfc1a847a3f13e5b2d0bcde64f02.nq.gz
│   ├── db8b2fe19a1c7fb3c53eac3a59761ab5c3398b93.nq.gz
│   ├── eb2f78ac2162a42f9ef44564f1a139056f1b25c1.nq.gz
│   ├── eef0cd928a5c048aacb542e78fb152a8ffd5f5fd.nq.gz
│   ├── f5eed9921354dd2be70ce75a1a70a93294c1e57d.nq.gz
│   ├── f99e3546000ce84654d6077218e652e138d2c15d.nq.gz
│   └── f9eed05e66582f609b0cb13ed315450f7558ca7f.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 029fbbf6e5f8b5a3e6ba2a22874d7264a18956e5.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 30 files
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

[huggingface/ipyh-optimization](https://github.com/huggingface/ipyh-optimization)

---
*Parsed on 2026-10-28 by [repolex](https://repolex.ai)*
