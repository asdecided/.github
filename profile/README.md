# AsDecided

> **Give your coding agent the decisions your team already made — so it stops re-doing things you ruled out.**

Agents that know *why*. **Deterministic. Read-only. No RAG, no guessing.**

AsDecided keeps a team's recorded knowledge — requirements, decisions, designs,
roadmaps, and prompts — as typed Markdown in the repo, validates it in CI, and
serves it read-only to coding agents over MCP. Retrieval is deterministic and
reproducible: no embeddings, no model call to decide what's relevant. The engine
underneath is **RAC — Requirements as Code**, open source and built to be
air-gapped; the trust boundary is human PR review, never the agent.

## Start here

```bash
brew install asdecided/tap/asdecided-core
decided quickstart
claude mcp add lore -- decided-mcp --root /path/to/your/repo
```

Full documentation: <https://asdecided.github.io/core/>

## The repositories

One repo per concern (ADR-092):

| Repository | What it is |
|---|---|
| [core](https://github.com/asdecided/core) | The native engine: the `decided` CLI, validation gates, and read-only MCP server |
| [spec](https://github.com/asdecided/spec) | Language-neutral schemas and compatibility fixtures |
| [ci](https://github.com/asdecided/ci) | Validation and gating wrappers, GitHub first |
| [sdk](https://github.com/asdecided/sdk) | Thin language clients over the engine's stable machine contracts |
| [connectors](https://github.com/asdecided/connectors) | Ancillary inbound and outbound integrations |
| [editors](https://github.com/asdecided/editors) | IDE and editor integrations |
| [benchmarks](https://github.com/asdecided/benchmarks) | Deterministic evaluation suites |
| [wayfinder-router](https://github.com/asdecided/wayfinder-router) | Deterministic prompt-complexity routing |
| [proofkeeper](https://github.com/asdecided/proofkeeper) | A bring-your-own-model verification agent |

## How the pieces fit

- **core** is the system of record: it captures *what* your product should
  do and *why*, and enforces it at write time (`decided validate`, `decided gate`).
- **Proofkeeper** closes the loop: it reads those capabilities over the
  published export contract, drives your product, and proposes verification
  evidence back by pull request.
- **Wayfinder** is a sibling, not a consumer — routing is a runtime concern,
  not a knowledge one. It began as an experiment inside RAC and was split out.
- Everything else (connectors, SDKs, editors, CI) is a thin surface over the
  engine's stable contracts — the engine stays deterministic, offline, and
  in one place.

## Principles

- **Markdown-first.** Every artifact is plain Markdown with a small
  frontmatter envelope, versioned next to the code.
- **Deterministic over probabilistic.** Classification, retrieval, routing,
  and eval scoring make no model calls; the same input gives the same answer.
- **Read-only at serve time.** Agents cite recorded decisions by ID; they
  cannot mutate the store. Changes land through human-reviewed PRs.
- **Enforced in CI.** Malformed artifacts, broken links, and references to
  superseded decisions are rejected before the knowledge lands.

## Project status

Everything here is early and evolving quickly. Contributions, ideas, and
experiments welcome — start with
[core](https://github.com/asdecided/core).
