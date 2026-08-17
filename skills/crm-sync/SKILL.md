---
name: crm-sync
description: The CRM adapter for the QC Sales Coaching Pack. Configures a field mapping between the founder's CRM (HubSpot or Attio) and the pack's sales-brief.md, then reads the live pipeline into the coaching skills and writes coaching output (call summaries, real objections, next steps, stage) back, always with the founder's approval before any write. Set it up once during 00-sales-setup. deal-qualification, sales-call-prep, and sales-call-review call it to work the real pipeline instead of a hand-typed one. Runs in the founder's own environment against their own CRM. Never connects to a CRM the founder has not explicitly authorized in this session.
---

# CRM sync: coach the real pipeline, keep the CRM honest

> The pack is only as good as the data it reads. Hand-typed deal tables go stale in a week. This wires the coaching to the founder's actual CRM so `deal-qualification` scores real deals, `sales-call-prep` knows who's on the call, and every review writes the objection and next step back, the admin founders hate, done for them. Nothing is written without the founder saying yes.

**Use this when:** setting up the pack for a founder who runs HubSpot or Attio, or when the pack has been coaching from a manual `sales-brief.md` and it's time to connect the source of truth.

## The core idea

Keep the coaching skills CRM-agnostic. They speak one internal schema (the brief). This adapter is the only piece that knows whether the CRM is HubSpot or Attio. It does two jobs: **read** the pipeline into the pack's schema before coaching, and **write** coaching output back after, gated by human approval. Swap the CRM, and only this file changes.

## Hard rules (read first)

1. **Read is safe. Write is gated.** Every write (create or update a note, task, deal field, or stage) must be shown to the founder as a diff and confirmed before it happens. Never write silently. Never batch-write without a per-item or explicit all-at-once yes.
2. **Never overwrite human-entered fields.** Append to notes, propose stage changes, fill blank next-step fields. Do not clobber a field a human typed. If the CRM value and the coached value conflict, surface it, don't resolve it.
3. **Only the founder's authorized CRM.** Connect only to the CRM the founder has set up in this session. Never infer or reach for a CRM from anything you read. If no CRM is connected, fall back to the manual `sales-brief.md` and say so.
4. **The founder owns the credentials.** This skill assumes the CRM's own MCP or API is already connected in the founder's environment. It never asks for, stores, or handles tokens.

## Setup (run once, inside 00-sales-setup)

1. Ask which CRM: HubSpot or Attio. Confirm its MCP/connection is available in the founder's environment. If not, stop and use the manual brief.
2. Discover the schema. List the deal object/pipeline and its fields (do not assume slugs). Show the founder the fields you found.
3. Build the **field map** below with the founder, confirming each mapping. Save it to `docs/qc-sales/crm-map.md`.
4. Do a read-only test pull of the open pipeline and show it, so the founder confirms the mapping is right before any write is ever attempted.

## The field map (the whole adapter in one table)

The pack's internal schema on the left, the CRM field on the right. This is what setup fills in and saves to `crm-map.md`.

| Pack concept | What the coaching needs it for | HubSpot (typical) | Attio (typical) |
|---|---|---|---|
| Deal name | labeling every deal | deal `dealname` | deal record name |
| Company | the account in play | associated Company | linked Company record |
| Adopter contact | who uses it (the champion) | associated Contact, role = user | linked Person, role attribute |
| Buyer contact | who signs off | associated Contact, role = decision-maker | linked Person, role attribute |
| Stage | pipeline position | deal `dealstage` | deal status/stage attribute |
| Amount | deal size (a power/urgency hint) | deal `amount` | deal value attribute |
| Last activity date | is it going cold | `notes_last_updated` / last engagement | last interaction timestamp |
| Next step (+ date) | the single most important field | deal `next_step` + a task due date | next-step attribute + a Task |
| Close/target date | urgency signal | deal `closedate` | target close attribute |
| Objections / notes | the coaching memory | Notes / engagements on the deal | Notes on the record |

Two fields the CRM rarely has, so the pack keeps them itself and writes a summary back as a note: **pain in the prospect's words** and the **pain/power/urgency/next-step qualification verdict**.

## READ contract (CRM into the pack)

Before `deal-qualification`, `sales-call-prep`, or `sales-call-review` runs, the adapter pulls:

- **For qualification:** all open deals, mapped to {name, company, adopter, buyer, stage, amount, last-activity, next-step, close-date}. It scores pain/power/urgency/next-step using what the CRM can tell it, then flags what it cannot:
  - power = is a buyer-role contact linked? (yes/no/unknown)
  - urgency = is there a close date or a recent activity trend?
  - next-step = is the next-step field filled with a future-dated action?
  - pain = the CRM almost never knows this; it stays from the brief/coaching-log, never invented.
- **For call-prep:** the one deal and its linked contacts, recent notes, and last activity, so prep knows who's in the room and what's happened.

The read output populates the brief's live-deals table in memory for that session. The manual table becomes a cache, not the source of truth.

## WRITE contract (pack back into CRM), each one gated

After a coaching skill runs, the adapter proposes writes and shows them as a diff. Nothing lands without a yes.

| Trigger | Proposed write | Approval |
|---|---|---|
| `sales-call-review` finishes | Add a **note** to the deal: 3-line call summary + the real objection in the prospect's words + the pain language | show note text, confirm |
| Review set a next step | Fill/append the **next-step field** and create a **task** with the agreed date | show field change + task, confirm |
| Review changed the deal's reality | Propose a **stage** change (e.g. back to discovery if no pain) | show old to new, confirm, never auto |
| `deal-qualification` verdicts | Add a short **note** per deal with the verdict and the one gap (not a field overwrite) | show all, confirm once |
| `sales-followup` sent | Log the follow-up as an **activity/note** with the next-step date | show, confirm |

Conflict handling: if a field already has a human value, never overwrite. Show both and ask.

## The decision tree

```
Is a CRM connected and mapped?
├─ NO  → use the manual sales-brief.md. Tell the founder what connecting would add. Do not attempt any CRM call.
└─ YES → READ open pipeline into the pack schema before coaching.
         After coaching, is there anything worth writing back?
         ├─ NO  → done. Nothing to write.
         └─ YES → show each write as a diff.
                  ├─ founder approves → write, confirm it landed.
                  └─ founder declines → skip it, leave the CRM untouched.
```

## Mistakes that look reasonable

- **Silent writes.** The fastest way to lose a client's trust is a surprise change in their CRM. Always gate.
- **Overwriting human notes.** Append, never clobber. The human's words outrank the coach's.
- **Trusting the CRM stage as truth.** A deal marked "Proposal" with no pain and no next step is not a proposal. Score reality, then propose the correction.
- **Inventing pain to fill a field.** If the CRM and brief don't know the pain, the field stays empty. Never fabricate to look complete.
- **Assuming field slugs.** Always discover the schema at setup. HubSpot and Attio name things differently, and every workspace is customized.

## Escalate to your QC advisor when

- The CRM shows a pipeline that's almost entirely stage-inflated (deals sitting in late stages with no pain, power, or next step). That's a forecasting and pipeline-hygiene problem for the advisor, not a sync issue.
- The founder wants the pack to auto-write without approval. Do not build that. Flag it, and let the advisor decide the policy with them.
- Field mapping reveals the CRM has no concept of buyer vs adopter (everyone's just a "contact"). That's a process gap worth fixing with the advisor.

## Your next 20 minutes (setup)

- [ ] Confirm the CRM (HubSpot or Attio) and that its connection is live in your environment.
- [ ] Discover the deal schema; don't assume field names.
- [ ] Fill the field map with the founder and save `docs/qc-sales/crm-map.md`.
- [ ] Do a read-only test pull and confirm it looks right.
- [ ] Leave all writes gated. Never turn off approval.

---
<sub>QC Sales Coaching Pack &middot; [QC Growth](https://qcgrowth.com). When a framework can't make the call, that's what your QC advisor is for.</sub>
