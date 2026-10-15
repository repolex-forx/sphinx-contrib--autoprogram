# Repolex Knowledge Graph of sphinx-contrib/autoprogram

RDF knowledge graph data for [sphinx-contrib/autoprogram](https://github.com/sphinx-contrib/autoprogram), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/autoprogram
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 80ecc511c9fd867e45bfb269ac9136e5444b5022
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 80ecc511c9fd867e45bfb269ac9136e5444b5022
│           └── chunk-001.nq.gz
├── blob
│   ├── 004c025d921faab720e439dae3a161459c13ffa2.nq.gz
│   ├── 0867d2213cf004f0e78ecfc342dfb53e62ec67d1.nq.gz
│   ├── 0eaffa25ebddaecf97bf436797bede6fdfa86ff3.nq.gz
│   ├── 2a9acf13daa95e85642ea255d3e3bd1ef8252804.nq.gz
│   ├── 38950131a85b8d610fadbe7a2f6ff0bd2cf992b3.nq.gz
│   ├── 40640097d287776c26d605665ea4073e5fa64480.nq.gz
│   ├── 471f29f7d38a34edaf87811db76e4630e1e4e466.nq.gz
│   ├── 49ec67b6396df3ed142d8c72514c400102dbf445.nq.gz
│   ├── 663cb164eab3310939ed547d167c598b2373befe.nq.gz
│   ├── 73331aaacf56573c4e0cbaf3828c6f1d012525a1.nq.gz
│   ├── 8841ac156196ea2b78894987513fec60e00efcb1.nq.gz
│   ├── 9602325e3f5d8283cf9918d67d3d1ee876c06757.nq.gz
│   ├── b0f5756bba2a298c5a118f8410bdbe70874a49cd.nq.gz
│   ├── bc94764751a2f5c4059dd85ff6f3b59eeb72c723.nq.gz
│   ├── c3a26d480f52d1adeb3772bb4249cb984725cf3f.nq.gz
│   ├── d9c73510b505fef7963fb1f8e9dc0612fbe26663.nq.gz
│   ├── df92699ec6df1c3e770d7d9ea9e0cec07173d728.nq.gz
│   ├── e13ec03c6c832efea6f4166e639101aca1e22b70.nq.gz
│   ├── f0223655734b9254db573372dd20cda89dd29cba.nq.gz
│   └── f6eb6f2aef2f954a0bcfaa52df1190f2e99a7b34.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 80ecc511c9fd867e45bfb269ac9136e5444b5022.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 28 files
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

[sphinx-contrib/autoprogram](https://github.com/sphinx-contrib/autoprogram)

---
*Parsed on 2026-10-15 by [repolex](https://repolex.ai)*
