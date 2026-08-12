---
name: cross-module-audit-after-per-task-review
description: Use when orchestrating multi-agent implementation with per-task review and deciding whether a final whole-branch audit is worth the cost
metadata:
  mneme-type: skill
  mneme-source: mneme-build@plans-01-07
  mneme-captured: 2026-08-12
  mneme-last-verified: 2026-08-12
---
# cross-module-audit-after-per-task-review

## Procedure

1. Keep per-task adversarial review (it keeps implementers honest — near-zero fix rounds).
2. After all tasks land, run two independent whole-branch auditors: one attacking correctness across module boundaries, one checking plan/spec compliance.
3. Give auditors concrete attack lanes drawn from the plan's trust boundaries, and require demonstrated findings only.
4. Route blocking findings through one fix pass plus an independent re-check.

## Failure pattern

Per-task review structurally cannot see cross-module composition bugs: in this build it missed a staging-store frontmatter injection, a date-in-hash dedup defeat, and a whole-file rewrite masquerading as a delta edit — every one caught by the whole-branch audit instead (all three recorded in CHANGELOG 0.2.0, Hardened section).
