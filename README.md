# Repolex Knowledge Graph of colcon/colcon-argcomplete

RDF knowledge graph data for [colcon/colcon-argcomplete](https://github.com/colcon/colcon-argcomplete), parsed by [repolex](https://repolex.ai).

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
rlex download colcon/colcon-argcomplete
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 4b8388fef875a1407af184be78088de90cbb4eba
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 4b8388fef875a1407af184be78088de90cbb4eba
│           └── chunk-001.nq.gz
├── blob
│   ├── 08ea7278f65afbb942c7a700885fc414f82feff9.nq.gz
│   ├── 1a48a567ae43276bd3874dd320c0987e240ddff7.nq.gz
│   ├── 2710b5f77d22cdc570e31d5e1b829a948a5d5549.nq.gz
│   ├── 326bb66d4c74f0cf8cf0dfc4e79909001f37da84.nq.gz
│   ├── 3b3d999beada7f02c37963dd70a0da633503d8d1.nq.gz
│   ├── 409bac4971e1f5d180e9c05d9adc40d636c01731.nq.gz
│   ├── 42b3f6c5149832aae69fb0a6eca96806313616d4.nq.gz
│   ├── 44ca35f7ad8bbf8225633386f4cf2203f107c8a0.nq.gz
│   ├── 63fdc120e7ffbe86cfbc246a33657adfa5853d0d.nq.gz
│   ├── 6d65665612e3c9e3c7f33a931322cd8524481d01.nq.gz
│   ├── 74e723b54e9d979bcf2638a4a3d44699d3909d4c.nq.gz
│   ├── 7d9223b31baea88c458f5dcc4f6a783454a5d820.nq.gz
│   ├── 8d315d51e4f6e4f533a08823b5cc3627e9540cc2.nq.gz
│   ├── 9a8e97acf459e18d7e90cb8a3ad69e14fca21555.nq.gz
│   ├── ad39b4c140d15fc22febb267b1a583214b5bd08f.nq.gz
│   ├── ba7634c0b6c83001b45dd0e547e728f1926eabfa.nq.gz
│   ├── d645695673349e3947e8e5ae42332d0ac3164cd7.nq.gz
│   ├── dffe460f162da9929178a7ce342532e7ba896425.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e840915a2bcc881e7c9f66846f720515931f749d.nq.gz
│   └── ff6a0032242da55d808076f33e5af6e079ee76e8.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 4b8388fef875a1407af184be78088de90cbb4eba.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 29 files
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

[colcon/colcon-argcomplete](https://github.com/colcon/colcon-argcomplete)

---
*Parsed on 2026-10-17 by [repolex](https://repolex.ai)*
