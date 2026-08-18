# Changelog

All notable changes to the QC Sales Coaching Pack. One person at QC owns this file and a quarterly refresh. A stale pack is worse than no pack.

## [0.2.1] · 2026-08-18

Standalone robustness.

- Every coaching skill now degrades gracefully when `docs/qc-sales/sales-brief.md` does not exist. Running a single skill on its own (before `00-sales-setup`) no longer blocks; the skill asks for the context it needs inline and continues. Fixes a tester hitting "I don't have a sales-brief" when testing a skill directly.
- README notes that no setup is required to test a single skill.

## [0.2.0] · 2026-08-13

Added the CRM adapter.

- `crm-sync`: maps the founder's HubSpot or Attio pipeline to the pack's `sales-brief.md` schema, reads live deals into `deal-qualification` / `sales-call-prep` / `sales-call-review`, and writes coaching output (call summaries, objections, next steps, stage) back. Every write is gated on the founder's approval; human-entered fields are never overwritten. Runs only against a CRM the founder has explicitly authorized in-session; falls back to the manual brief when none is connected.
- `00-sales-setup`: now offers CRM setup as an optional step and hands off to `crm-sync`.

## [0.1.0] · 2026-08-13

First internal release. House layer, ready to deploy per engagement.

- `00-sales-setup`: builds `sales-brief.md` and `coaching-log.md`; reads an existing gtm-cofounder `founder-brief.md` if present.
- `sales-call-prep`: pre-call goal, three questions, target next step, pre-loaded objections, one pattern to watch.
- `sales-call-review`: honest post-call coaching pass; appends recurring patterns to the coaching log; feeds the brief.
- `sales-followup`: the four-part follow-up that sets a next step; stall handling.
- `objection-handling`: founder-led objection playbook (surface, don't spin); disqualifier tests.
- `deal-qualification`: pain / power / urgency / next-step triage; when to walk.

Escalation gates in every skill route the founder back to their QC advisor on anything above the pack's pay grade (pricing, competitive bake-offs, security reviews, ICP or motion problems, recurring unmoved patterns).

### Notes for the next version
- Consider a `pricing-conversation` skill (currently an escalation, deliberately).
- Consider a lightweight weekly `pipeline-review` that reads the whole deals table and reports movement.
- Watch whether founders actually update `coaching-log.md`; if not, bake the update deeper into `sales-call-review`.
