# AsDecided

> **Repository-native decision infrastructure for AI coding agents.**

AsDecided keeps human-reviewed engineering decisions beside the code as
validated Markdown, retrieves the current records that apply to a task, and
connects objective consequences to deterministic checks. Agents receive
inspectable authority with stable citations instead of a larger prompt or a
model judgement presented as proof.

[Product site](https://asdecided.com/) · [Documentation](https://asdecided.com/docs/start-here/) · [Canonical sources](https://asdecided.com/sources) · [Changelog](https://asdecided.com/changelog)

## Start here

```bash
brew install asdecided/tap/asdecided-core
decided quickstart
decided validate decisions/
decided gate decisions/ --code --base origin/main
```

Then [connect a coding agent](https://asdecided.com/docs/vendor/core/mcp/) to
the read-only MCP server.

## Record, retrieve, cite, enforce

- **Record:** preserve context, scope, lifecycle, alternatives and consequences in reviewable decision artifacts.
- **Retrieve:** resolve current applicable authority deterministically by repository, path or capability.
- **Cite:** attach stable decision IDs and source paths to plans, pull requests and review evidence.
- **Enforce:** link mechanically checkable consequences to architecture tests, policy and CI without an LLM judge.

Core requires no embeddings, hosted index or model call for retrieval. The
same repository state produces the same answer.

## Public repositories

| Repository | Responsibility |
|---|---|
| [core](https://github.com/asdecided/core) | Native `decided` CLI, validation gates and read-only MCP server |
| [spec](https://github.com/asdecided/spec) | Language-neutral decision-artifact contract and compatibility fixtures |
| [ci](https://github.com/asdecided/ci) | Decision-aware validation and merge-gate integrations |
| [sentry](https://github.com/asdecided/sentry) | Deterministic decision enforcement against code changes |
| [sdk](https://github.com/asdecided/sdk) | Thin language clients over stable engine contracts |
| [connectors](https://github.com/asdecided/connectors) | Explicit inbound and outbound bridges |
| [benchmarks](https://github.com/asdecided/benchmarks) | Reproducible evaluation and scale evidence |
| [proofkeeper](https://github.com/asdecided/proofkeeper) | Requirement-to-test verification companion |

## Source boundaries

- The [specification](https://asdecided.com/docs/spec/) governs the language-neutral artifact contract.
- The [documentation](https://asdecided.com/docs/start-here/) governs current commands and supported behaviour.
- Public repositories expose implementation evidence.
- The [changelog](https://asdecided.com/changelog) records dated released behaviour.
- [Notes](https://asdecided.com/notes) and [Articles](https://asdecided.com/articles) explain patterns and trade-offs; they do not override product authority.

The [canonical source map](https://asdecided.com/sources) gives people, search
engines and answer systems one route from a claim to the source that proves it.

## Principles

- **Markdown beside the code.** Decisions remain portable, diffable and reviewable.
- **Deterministic retrieval.** Current scope and lifecycle are resolved without a model call.
- **Read-only serving.** Agents retrieve and cite; accepted authority changes through repository review.
- **Truthful enforcement.** Mechanical checks prove only the consequences they can inspect.

AsDecided is open source, solo-maintained and supported on a best-effort basis.
Start with [Core](https://github.com/asdecided/core) or read the
[five-minute quickstart](https://asdecided.com/docs/vendor/core/quickstart/).
