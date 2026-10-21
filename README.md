# Repolex Knowledge Graph of glue-viz/glue-exp

RDF knowledge graph data for [glue-viz/glue-exp](https://github.com/glue-viz/glue-exp), parsed by [repolex](https://repolex.ai).

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
rlex download glue-viz/glue-exp
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 23914e7382039fa9d1f0f2640b8d7586c3265d81
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 23914e7382039fa9d1f0f2640b8d7586c3265d81
│           └── chunk-001.nq.gz
├── blob
│   ├── 1f573e52ef04f969664ca6bc841696500485326f.nq.gz
│   ├── 1f740a53fd80153c6d78443aad0f38c9e5233f71.nq.gz
│   ├── 212d4c469e48d7fde7c2381c1e25583a588cb50a.nq.gz
│   ├── 25fa942bc6bf296c6a7aa1d7127dcfcf964f46dd.nq.gz
│   ├── 306cf444300aa318e3ee58c099e73a4577a66a31.nq.gz
│   ├── 34d4b42c13527b12fe35e473e0af0b8085877587.nq.gz
│   ├── 495fd00a3d9d490fec8410edb8bf39e16293bd10.nq.gz
│   ├── 585b2599674520ee64ab58f93ed2dcf3b0e98a46.nq.gz
│   ├── 5bde9542f03b268caa0623166779dcab7d0c56e8.nq.gz
│   ├── 5cddb9621c02a11934044d33ea66f4b94ea501d3.nq.gz
│   ├── 6286eecd306849b31c7d70e1fc58d6884580a464.nq.gz
│   ├── 629fc8afbeb6ec48e5a3adb84c376218415ae4c5.nq.gz
│   ├── 6f23d838a289609e838521e7cc11a787b7b1e69b.nq.gz
│   ├── 7868275d8ef44267548bc539dc65bd5694a7efe6.nq.gz
│   ├── 84ce4bf15f2bed1eaa6308fa949f5c1b524ffdce.nq.gz
│   ├── 86f1282616f3b8285fc10b82628085f3284f5911.nq.gz
│   ├── 8d445604a95ac6a51874b6a1cbc812920719839a.nq.gz
│   ├── 97a7cfedf4f3fe16048220eb11a32eaeeed2ac93.nq.gz
│   ├── a228f2f9214ce7d4172ef1e08952795752ab243a.nq.gz
│   ├── b01a3cf77c981117d7f74b197dd6f21c6ed26100.nq.gz
│   ├── b7d5135191acdc54b7ce8c427b7c9ce3f8442ec5.nq.gz
│   ├── cc2c26e97cc41766a3eca6ecb5f397b7be0edc9f.nq.gz
│   ├── cdec13a5db31a64e80daaab5567c2a736383870b.nq.gz
│   ├── dbe775f5ea399f26eaf84e34b450f8b464a69d34.nq.gz
│   ├── e286e7366d8c1dc698011b90b01a6e30f9d98304.nq.gz
│   ├── e3c43a237737271e1cebfb57cd48c335e79c7848.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e86e6561fc792e6ba43484dc5fa1774fa577a992.nq.gz
│   ├── efc126467538180d44b3ba9331503dacc0deaa79.nq.gz
│   ├── fe4826cdd198fdbe2b69ad0d31390d5a02c86c13.nq.gz
│   └── ff37b434ab1ce490f1a7b8ba1bff156f7018619a.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 23914e7382039fa9d1f0f2640b8d7586c3265d81.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 39 files
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

[glue-viz/glue-exp](https://github.com/glue-viz/glue-exp)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
