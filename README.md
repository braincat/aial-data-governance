# AIAL Data Governance — How We Do It

> Published practice note from AIArchLab (AIAL), a human-led AI team. Author: InfoArc (Information Architect) · Published by: GSpark (System Architect) · 2026-11-01 · v1.0.
> This is the practice note as published internally; portfolio copywriting by BizAst is pending and will land as a separate polished version.

**One-line principle: every piece of data has exactly one authoritative copy, one name, one definition. Everything else is a reference or a derivative.**

What makes this note different from a policy document: **all five mechanisms below were running, with audit evidence, on the day it was written.**

## The five mechanisms

1. **Location map — every asset has an id.** A numbered map (L-001…) records type, purpose, authority status, owner, lifecycle, and known traps for every storage location. Look up before you guess. A 404 is not "doesn't exist" — permissions, wrong coordinate, and lifecycle are ruled out first.

2. **Delivery ledger — claims must survive hashing.** Every delivery claim registers three facts: Drive file id, sha256 read-back verification, and owner. An independent read-only account re-verifies existence and hash; claims without coordinates are recorded as *not delivered*.

3. **Single source of truth for trust scores.** Member trust scores have exactly one input and query location; every other scoreboard is a deprecated mirror. Only the chairman adjudicates changes; the governed member self-registers; governance audits but never edits the ledger.

4. **External asset governance — violations leave a permanent ledger.** Creating assets on external services is an environment change requiring an approved plan first. First case study: an unauthorized repo tracked from creation → registration (pending-delete) → chairman deletion → independent API verification (404) → closed as deleted, with the full audit trail preserved and the id never reused. Violations are not erasable — by design.

5. **Identity by registry, not by name.** Bot identity is always determined by reading the integration registry (botId ↔ name ↔ workspace ↔ permissions), never by session names or memory — this once caught two bots whose ids had been transcribed swapped.

## Operating rules (excerpt, G-001..G-022)
- Never read a truncated list or an error response as "no results"; if there is a next page, turn it.
- Deletions are always escalated; completion claims must be backed by API write + read-back.
- Governance rule changes: draft + impact list first, chairman approval, versioned release, rollback on veto.
- Each agent uses only its own credentials; cross-member work is content hosting, never credential sharing.

## Cost ledger (one day)
2 rules published + 1 tightened · 2 locations registered + 1 closed · 3 delivery verifications (2 PASS / 1 blocked as not-delivered) · 2 gaps escalated with one-click fixes attached.

> Principles don't announce themselves. The ledger speaks.

---
© AIArchLab (AIAL). Published practice note; licensing to be finalized.
