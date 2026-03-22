# Repolex Knowledge Graph of wolever/pprintpp

RDF knowledge graph data for [wolever/pprintpp](https://github.com/wolever/pprintpp), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [lexq](https://github.com/repolex-ai/lexq) query tool using [uv](https://docs.astral.sh/uv/getting-started/installation/).

If you have uv installed, just copy/paste this into your terminal:

```bash
uv tool install git+https://github.com/repolex-ai/lexq
```

This installs lexq onto your system, in your user context. Verify the install:

```bash
lexq --help
```

**lexq is designed to be used primarily by LLMs in a terminal.** Start up your favorite LLM and ask it to use the lexq tool. It's that easy!

To load this repo's data:

```bash
lexq download wolever/pprintpp
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 362d5be3ac8ea83d02762add582c9b2ba81ffbfa.nq.gz
│   ├── lsp
│   │   └── 362d5be3ac8ea83d02762add582c9b2ba81ffbfa.nq.gz
│   └── repolex
│       └── 362d5be3ac8ea83d02762add582c9b2ba81ffbfa.nq.gz
├── blob
│   ├── 081ac5d2c036a9fb7b764376b11aa47c4b6e1ee9.nq.gz
│   ├── 1856784fc2ac91cb3b590e54dcb24ac1ba902dba.nq.gz
│   ├── 2a9acf13daa95e85642ea255d3e3bd1ef8252804.nq.gz
│   ├── 3c59a00e005024bc423d424791f9a7fd1ac152eb.nq.gz
│   ├── 541171f2e420acc231be41a8bed9edca41327eb6.nq.gz
│   ├── 5dc130ecebbfc692eb80e304b2f7063740bf4d81.nq.gz
│   ├── 64b85d7d5b21b2a1072af79f2ad5b1fd1b339592.nq.gz
│   ├── 8bb77d455a66ff9636950d1ef9387a9ab77ddfcc.nq.gz
│   ├── 9561fb1061f6de114633c70871232a6896dcbe8a.nq.gz
│   ├── 966c9de131bb3ded3cc2124f49dd2f4dcccccf43.nq.gz
│   ├── a7631db84237af7a200440146cb3cfe30978db27.nq.gz
│   ├── d1828e9c75663b723dc5c5d4259648090972f5ad.nq.gz
│   ├── df25941b3c1f79c091deb8b0968f0de4592fd05b.nq.gz
│   ├── e194976cb9762f343d9f7cc77bb52046440d9150.nq.gz
│   ├── ed8195f5a6b8ef77cb34a1bfca98d1c3a56b2b6d.nq.gz
│   └── f3eb68308cc24634c1a572c81c45b999c8734b04.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 362d5be3ac8ea83d02762add582c9b2ba81ffbfa.nq.gz
├── filetree
│   └── 362d5be3ac8ea83d02762add582c9b2ba81ffbfa.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 26 files
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

## Source repository

[wolever/pprintpp](https://github.com/wolever/pprintpp)

---
*Parsed on 2026-03-22 by [repolex](https://repolex.ai)*
