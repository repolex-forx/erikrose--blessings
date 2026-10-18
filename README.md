# Repolex Knowledge Graph of erikrose/blessings

RDF knowledge graph data for [erikrose/blessings](https://github.com/erikrose/blessings), parsed by [repolex](https://repolex.ai).

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
rlex download erikrose/blessings
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 50655345d28627b6fe00210afa253ed0551c8dee
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 50655345d28627b6fe00210afa253ed0551c8dee
│           └── chunk-001.nq.gz
├── blob
│   ├── 0af1f0d70471d06526173f6599db9b3e9439eb93.nq.gz
│   ├── 107a6263f37a4121bb30247a49a4bb95c9232aa7.nq.gz
│   ├── 3d3a44e65b8c1b19f226714a460ee708cbf1e633.nq.gz
│   ├── 3e2fcf09f5bd0fd5322b2a9bb3596604493753ef.nq.gz
│   ├── 45e5781cb2b3001a3802074c81ed9064c3888ac6.nq.gz
│   ├── 5527fffbc89ccde2b1bdac88ae10799ea0ea4684.nq.gz
│   ├── 63ee5be921bc5758ecca3d938f4887cf92053889.nq.gz
│   ├── 94748175b9486be489e9568cf1cdb8fafc0aa36f.nq.gz
│   ├── af98c0d8771012024562d790ff8aa1c741d8b8bf.nq.gz
│   ├── b849aac183e699b6203ae1707e7be86dc5d7791a.nq.gz
│   ├── be17e5315746fc352f8f666ef78f76d1645896a5.nq.gz
│   ├── c1d668a3a6ba140bd304a3733b4a7a1a56f20478.nq.gz
│   ├── c24653f082c0757f5c5c6c866a7baf5d149bc72b.nq.gz
│   └── f963d06ab97762cf4894ed1e236813b93df0a34b.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 50655345d28627b6fe00210afa253ed0551c8dee.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 22 files
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

[erikrose/blessings](https://github.com/erikrose/blessings)

---
*Parsed on 2026-10-18 by [repolex](https://repolex.ai)*
