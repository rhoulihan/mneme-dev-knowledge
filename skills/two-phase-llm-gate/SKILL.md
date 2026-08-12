---
name: two-phase-llm-gate
description: Use when an LLM must contribute content to a persistent store and you need the store protected from model failure modes
metadata:
  mneme-type: skill
  mneme-source: mneme-build@plans-01-07
  mneme-captured: 2026-08-12
  mneme-last-verified: 2026-08-12
---
# two-phase-llm-gate

## Procedure

1. Split the flow: a 'prepare' step assembles the prompt bundle deterministically; the LLM returns STRUCTURED PROPOSALS only; an 'ingest' step validates, renders canonically, scans, dedups, and stages in tested code.
2. Treat every proposal field as untrusted input: enum/length/shape validation, size caps, secret scan, canonical rendering by construction.
3. Hash on semantic content (strip your own stamps like dates and session labels) so decline/dedup ledgers survive across days and sessions.

## Failure pattern

Letting the model write the store directly invites context collapse and format drift; even with proposals, hashing date-stamped renderings meant declined items resurfaced the next day with fresh hashes until semantic hashing landed.
