# Contributing to LIVECORE

LIVECORE is currently in product and architecture planning. Contributions should improve clarity, testability, safety, interoperability and maintainability.

## Before contributing

- Read the [Master Plan](docs/MASTER_PLAN.md), [Architecture](docs/ARCHITECTURE.md) and [Decision Register](docs/DECISIONS.md).
- Check whether a proposal conflicts with an accepted baseline decision.
- For consequential changes, open an issue or draft an Architecture Decision Record before implementation.

## Engineering expectations

- Keep real-time code isolated from blocking I/O, unbounded allocation and best-effort workloads.
- Define resource limits and failure behavior for plugins, adapters and agents.
- Use versioned interfaces and document compatibility/migration.
- Include tests, measurable acceptance criteria and failure-injection coverage where appropriate.
- Never claim hardware compatibility or production readiness without evidence.
- Preserve offline operation of critical functions.
- Treat security, privacy, accessibility and documentation as part of feature completion.

## Pull requests

A pull request should explain:
- Problem and user impact
- Design and alternatives
- Real-time, reliability, safety and security impact
- Tests and evidence
- Compatibility and migration implications
- Documentation updates and rollback

## Reporting vulnerabilities

Do not publish exploit details for an unresolved vulnerability in a public issue. Use the repository's private security reporting channel when configured; otherwise contact the maintainers privately and provide enough detail for responsible triage.

## Code of conduct

Be respectful, precise and constructive. Disagreement about technical direction is welcome; personal attacks, harassment and disclosure of private production data are not.
