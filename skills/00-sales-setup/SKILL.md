---
name: 00-sales-setup
description: One-time setup for the QC Sales Coaching Pack. Interviews the founder to build a sales-brief.md (their motion, who adopts vs who pays, price, the deals in flight, ICP fit, the problem they kill, known objections, competitors) and starts a coaching-log.md that tracks patterns across calls. Every other QC sales skill reads these first, so coaching is about their business, not a template. Run this once before using sales-call-prep, sales-call-review, sales-followup, objection-handling, or deal-qualification. Reads an existing founder-brief.md if the founder already has one, to avoid re-asking.
---

# Sales setup: build the brief the coach reads first

> A coach who doesn't know your business gives textbook advice. This is the one-time step that makes every other skill in the pack coach *your* deals: your motion, your buyer, your price, your objections. It takes about ten minutes and it is the difference between a generic sales bot and a QC coach who knows your pipeline.

**Use this when:** the founder is starting with the QC Sales Coaching Pack, before any other skill.

## The core idea

Every other skill in this pack reads `docs/qc-sales/sales-brief.md` before it says a word. This skill writes it. Get the founder's real motion, buyer, and deals on paper once, tag what's known versus guessed, and from then on the coaching is specific from the first minute.

If a `docs/gtm-cofounder/founder-brief.md` already exists (from the public GTM pack), read it first and pull ICP, positioning, and the problem killed from there. Do not re-ask what you can already answer. Confirm it with the founder, then only ask the sales-specific gaps.

## How to run this (for the agent)

1. Check for an existing `docs/gtm-cofounder/founder-brief.md`. If present, read it and pre-fill everything you can. Tell the founder what you already know and ask them to confirm or correct it.
2. Ask the sales-specific questions below, one at a time, conversationally. Do not dump a form. Let them answer in their own words.
3. Tag every fact `[validated]` (confirmed by a real deal, a real customer, or real data) or `[assumption]` (the founder's belief, not yet tested). When in doubt it is an assumption.
4. Write `docs/qc-sales/sales-brief.md` in the structure below.
5. Create `docs/qc-sales/coaching-log.md` with the empty template at the bottom.
6. Ask if the founder runs a CRM (HubSpot or Attio). If yes, hand off to `crm-sync` to build the field map now, so the pack reads the real pipeline instead of a hand-typed table. If no, the manual brief is the source of truth.
7. End by telling the founder the next skill to run: `sales-call-prep` if they have a call booked, or `deal-qualification` if they want to triage the pipeline first.

## The questions (ask only what the brief doesn't already answer)

**The motion**
- How does a deal actually happen today? A developer tries it, then someone buys? Or you sell top-down to a buyer first? Or there is no repeatable pattern yet?
- Is there a price, and what is it? Roughly what does a deal close for?
- How long from first contact to closed, when it has happened?

**Who adopts vs who pays**
- Who is the person who uses the product day to day (role, seniority)?
- Who signs off on paying (role)? Are they the same person or a different one?
- On your recent calls, which of those two were you actually talking to?

**The deals in flight**
- Walk me through every live deal: company, who you're talking to, what stage, when you last spoke, and what the agreed next step is (if any).

**ICP fit**
- What does a genuinely good-fit prospect look like? Company type, stage, trigger that put them in pain.
- Who looks like a fit but is a time sink? The disqualifiers.

**The problem and the objections**
- In the customer's own words, what painful problem does this kill?
- What are the objections and stalls you hear most? Quote them if you can.
- Who or what are you really competing with? A rival tool, the status quo, "we'll build it ourselves," "not now"?

## The self-check before you save

Before writing the brief, confirm:
- Every fact is tagged `[validated]` or `[assumption]`.
- You did not invent a price, a cycle length, or an ICP the founder didn't give you. Blanks stay blank, marked "not yet known."
- The buyer-vs-adopter distinction is explicit. This is the single most common thing founders blur, and it breaks all downstream coaching if it's wrong.

## sales-brief.md structure

```
# Sales Brief: [Company]
_Last updated: [date]. Tags: [validated] = confirmed by a real deal/customer/data. [assumption] = belief, not yet tested._

## Product in one line
[what it is, for whom]

## Motion
- Type: [bottom-up / top-down / no repeatable pattern yet] [tag]
- Price: [amount, or "not yet known"] [tag]
- Cycle: [length, or "not yet known"] [tag]

## Who adopts vs who pays
- Adopter: [role] [tag]
- Buyer: [role] [tag]
- Same person? [yes/no/unknown]

## The problem we kill (customer words)
[quote] [tag]

## ICP fit
- Good fit: [criteria + trigger] [tag]
- Disqualifiers: [criteria] [tag]

## Competition / alternative
[rival / status quo / build-it / not-now] [tag]

## Known objections (running list, their words)
- "[objection]" [tag]

## Live deals
| Company | Contact (role) | Stage | Last touch | Next step |
|---|---|---|---|---|
| ... | ... | ... | ... | ... |
```

## Escalate to your QC advisor when

- The founder can't describe a single repeatable way deals happen. That's a strategy problem (motion and ICP), above this pack. Flag it for the advisor.
- There is no price and no plan for one. Pricing strategy is an advisor conversation, not a setup field.

## coaching-log.md template

```
# Coaching Log: [Company]
_Recurring patterns across calls. sales-call-review appends here. Read before coaching._

## Recurring patterns
(none yet)

## Wins to keep
(none yet)

## Open objections to prep
(none yet)
```

---
<sub>QC Sales Coaching Pack · [QC Growth](https://qcgrowth.com). When a framework can't make the call, that's what your QC advisor is for.</sub>
