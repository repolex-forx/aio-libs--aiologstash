# Repolex Knowledge Graph of aio-libs/aiologstash

RDF knowledge graph data for [aio-libs/aiologstash](https://github.com/aio-libs/aiologstash), parsed by [repolex](https://repolex.ai).

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
rlex download aio-libs/aiologstash
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 61c8f784c590336406a1c1975bf9c5381adfa6ef
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 61c8f784c590336406a1c1975bf9c5381adfa6ef
│           └── chunk-001.nq.gz
├── blob
│   ├── 01c54f8a69bdb62a7addbe9b5bbf940f5ed2a79a.nq.gz
│   ├── 039546e6aa165a36e90b732b0aa6ad240d28d722.nq.gz
│   ├── 13ff0bb0c757e3ba1e16a903177e77466c7b5503.nq.gz
│   ├── 288ea9dc0f8d36d89dc428218c4e90fb21a80f56.nq.gz
│   ├── 2e9a28ef33831a15540ab49b29ff54be4be27c69.nq.gz
│   ├── 457ad5ea20cf8078fb1a7662e888ccc1c482b464.nq.gz
│   ├── 4d2e014bc1c5fa762465a67d18c178fbbd771f81.nq.gz
│   ├── 4d2fdd8fa16d879abf7c82b55454796313b491d7.nq.gz
│   ├── 4e7f10aee7a06110e7c2747be0a5310807efbe73.nq.gz
│   ├── 6ea20650afd318e6f414b05025314b348b228afc.nq.gz
│   ├── 744c33beb8a4e02eb95adbbfaa8ba6dbafb5fafa.nq.gz
│   ├── 7bbc71c09205c78d790739d246bbe4f9f1881c17.nq.gz
│   ├── 7bdaebb68db43a55812b57bc7dc3d4f9e0300d63.nq.gz
│   ├── 844b09e7ee6db4f32f1180a077dcea770da31f88.nq.gz
│   ├── 861f67fbc2cc5487c916d946faf7e7e49bcf97c1.nq.gz
│   ├── 8e0d05624e059ad140d222d95a73491e76a3bf39.nq.gz
│   ├── 92f9a0bc885e2c55cde2a9c3e03285d745a8ab84.nq.gz
│   ├── b1d59388077a8a8a2cad4557cfd231abd64b434c.nq.gz
│   ├── b6d27446ecdd91a0ca94f6c16338948e66af5d46.nq.gz
│   ├── bce5f627f97b8cb09e5668efa802d35537fce61d.nq.gz
│   ├── d11af7822d33d3baf27d0943933498894d3783f6.nq.gz
│   ├── e78cd4917c9e020838c69d236d2a8067e369c1ae.nq.gz
│   ├── ee3b2ba63d01909bd641bf40d75ccbc216d29dd6.nq.gz
│   ├── f2cd14691c373ec2b0f4ee9c5b9eeccc737361fc.nq.gz
│   └── f4572339b970c63ed56fd068602d35e2be8933c5.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 61c8f784c590336406a1c1975bf9c5381adfa6ef.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 33 files
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

[aio-libs/aiologstash](https://github.com/aio-libs/aiologstash)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
