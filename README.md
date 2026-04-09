# Repolex Knowledge Graph of Anorov/PySocks

RDF knowledge graph data for [Anorov/PySocks](https://github.com/Anorov/PySocks), parsed by [repolex](https://repolex.ai).

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
lexq download Anorov/PySocks
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 524ceb4b4fb20b07994a5b1e34fecba3f8995073
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 524ceb4b4fb20b07994a5b1e34fecba3f8995073.nq.gz
│   └── repolex
│       └── 524ceb4b4fb20b07994a5b1e34fecba3f8995073
│           └── chunk-001.nq.gz
├── blob
│   ├── 04b6b1f37c4dffb82942cdcc2b77092798ca4aa2.nq.gz
│   ├── 15020d204074f5976b82d65cf2a60dd72ecbc53f.nq.gz
│   ├── 15712ed9440a24567ef42830bb79d32485b97170.nq.gz
│   ├── 18edef1aa6c01df9d19700e181e3f6b3fe77bfb9.nq.gz
│   ├── 26b6e7b6eff4dae7b2e965fd84e1699ed7c902e3.nq.gz
│   ├── 26c83439cc50ea607cd1853da16caf0f9ed06bcb.nq.gz
│   ├── 2774c720946c006f7856bf1641d8b0b1a916b94d.nq.gz
│   ├── 3b84f2109e936d84743f940eef4fb6dbd7104490.nq.gz
│   ├── 4710bf9d0b26ef9642f6822b0c88bac49b20c00d.nq.gz
│   ├── 49893b221ca7f7de3cdc8398dd81735e3124ec6b.nq.gz
│   ├── 7bcf590d2d7368e5407568529bc8d8b889bc101f.nq.gz
│   ├── 7e98dfc5074f4533a8169c755eb627934d365462.nq.gz
│   ├── b2923a6bc0ab47433048016acc0c0d314db27e2d.nq.gz
│   ├── c9462cccb51039cc8ecdf75adde2a57c972122cd.nq.gz
│   ├── d69d6f3b3c759a05f23145430b4691c4a74d140f.nq.gz
│   ├── db6de517fca8101a0a39aaef98a0241849c027bf.nq.gz
│   ├── e67c98d7af97cd17bbc3a36800ad0ae94200435c.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── f170155820ba33360282b3d4ef7dc8acbaaf224c.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 524ceb4b4fb20b07994a5b1e34fecba3f8995073.nq.gz
├── filetree
│   └── 524ceb4b4fb20b07994a5b1e34fecba3f8995073.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 29 files
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

[Anorov/PySocks](https://github.com/Anorov/PySocks)

---
*Parsed on 2026-04-09 by [repolex](https://repolex.ai)*
