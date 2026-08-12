# mneme-dev-knowledge — knowledge scope

**Sensitivity:** internal
**Contribution mode:** commit
**Maintainers:** rhoulihan

## Scope statement

Development knowledge from building mneme itself: multi-agent TDD orchestration patterns, Claude Code platform behaviors (hooks, plugin manifests, YAML frontmatter), and Python stdlib gotchas (sqlite3, argparse, packaging) discovered while building the engine.

## What belongs here

- Hard-won procedures (skills): verified fixes, deployment paths, debugging golden paths — each with the failure pattern that made it non-obvious.
- Durable facts: constraints, gotchas, decisions, runbook notes that stay true across tickets.

## What does NOT belong here

- One-off decisions tied to a single ticket or conversation.
- Secrets, credentials, tokens, or personal data — the capture pipeline blocks them, and so does CI.
- Anything derivable from public documentation.

## Routing

This scope statement is the routing prompt: mneme's distiller matches candidate knowledge
against it. Keep it specific — name the products, systems, and processes this plugin covers.
