# Contributing knowledge to mneme-dev-knowledge

Knowledge enters this repo through pull requests — human-written or staged by mneme's
curated harvest. Either way the same rules apply.

## The promotion rule

A contribution must carry:

1. **Verified success** — the procedure or fact was actually exercised, not assumed.
2. **A named failure pattern** — what went wrong before the fix; the dead ends eliminated.
3. **Non-obviousness** — not derivable from public documentation.

## Format

- Skills: `skills/<name>/SKILL.md`, kebab-case `name` matching the directory,
  trigger-rich `description` (it IS the retrieval surface), provenance in `metadata`.
- Facts: one topic per file in `facts/`, typed bullets
  (`decision | constraint | gotcha | runbook-note | reference`), tags, verified dates.
- Delta edits only — never regenerate whole files.

CI (`validate.yml`) lints format and scans for secrets, so review can focus on substance.

## Review policy

- CODEOWNERS routes each area to its maintainers.
- Unreviewed AI-generated bulk contributions are closed without merge; every PR needs a
  human who vouches for the promotion rule above.
- Merges bump the plugin version automatically — accepted knowledge ships immediately.
