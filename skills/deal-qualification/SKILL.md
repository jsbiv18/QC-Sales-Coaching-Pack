---
name: deal-qualification
description: Triage a founder's pipeline so they know which deals are real, which are hope, and what the single next move is for each. A simple honest qualification frame for founder-led dev-tool sales (pain, power, urgency, next step), plus when to walk away. Kills pipeline theater. Use when the founder has a list of "warm" deals and can't tell what's real, or before forecasting. Reads and updates the live-deals table in sales-brief.md.
---

# Is this deal real? Qualify so you stop chasing ghosts

> Founders confuse activity with pipeline. A stack of "warm" conversations feels like progress and forecasts like revenue, then closes like nothing. This is the honest triage: for every deal, real, maybe, or dead, and the one next move. Fewer real deals worked hard beats twenty warm ones nursed.

**Use this when:** the founder has several live conversations and can't tell which deserve their time, or they're about to tell someone (a board, an advisor, themselves) what's going to close.

## The core idea

A real founder-led deal has four things. Miss one and it's not real yet, it's a maybe with a specific gap to close. The value of qualifying isn't to kill deals, it's to tell the founder the *one thing* each deal is missing so they work the gap instead of sending another "just checking in."

The four:
1. **Pain.** They described a real, painful problem in their own words. Not "interesting," pain.
2. **Power.** You're talking to (or have a path to) the person who can actually say yes and fund it.
3. **Urgency.** There's a reason to act now, a trigger, a deadline, a cost of waiting. Without it, "yes" lives forever in "later."
4. **Next step.** There's a specific, scheduled next action with a date. No next step means no deal, however warm.

Reads and updates the **Live deals** table in `docs/qc-sales/sales-brief.md`.

## How to run this (for the agent)

1. Read the sales brief, especially the live-deals table and the ICP.
2. For each deal, ask the founder what they know against the four (pain, power, urgency, next step). Don't accept vibes; ask for the evidence ("what did they actually say?").
3. Score each deal real / maybe / dead using the rule below, and name the single gap and the single next move.
4. Be honest. The founder's optimism is the enemy here. A deal with no power and no next step is dead even if the last call was lovely.
5. Update the live-deals table with the new stage and next step.

## The scoring rule

```
Count how many of the four this deal has (pain, power, urgency, next step):

4 of 4          → REAL. Drive it. Next move = execute the scheduled next step well.
Pain + 2 others → MAYBE. Name the missing one; the next move is to close that gap.
Pain only       → EARLY. Real problem, nothing else yet. Next move = get to power, or build urgency.
No pain          → DEAD (as a deal). It's a nice conversation. Requalify or let it go.
No next step     → treat as at-risk regardless of the rest. Set one today or it drifts to dead.
```

Note the asymmetry: **no pain is dead, no next step is at-risk, missing power or urgency is a maybe with a clear gap.** Pain is the one you cannot manufacture.

## The output

For each deal, three lines:
- **Verdict:** real / maybe / early / dead, with the count.
- **The gap:** the single most important missing thing (or "none, it's real").
- **The one next move:** specific and dated. "Get the VP Eng on a 20-min call by Friday," not "nurture."

Then one portfolio line: where the founder should spend the next week. Usually: pour time into the one or two real deals, close the single gap on the maybes, stop hand-holding the dead ones.

## When to walk away

Walking is a skill, not a failure. Walk (or park with a real future trigger) when:
- No pain after a genuine discovery attempt. You're selling to someone comfortable.
- No path to power after asking, and your champion can't or won't get you there.
- Endless "maybe" with no trigger you can point to. Time spent here is time stolen from real deals.

A clean "this doesn't sound like the right time, here's when to come back" often earns more respect (and later revenue) than months of nudging.

## Mistakes that look reasonable

- **Counting activity as pipeline.** Ten calls booked is not ten deals. Qualify before you forecast.
- **Happy ears in aggregate.** One warm deal is optimism; a pipeline of warm-but-unqualified is self-deception.
- **Chasing the biggest logo regardless of fit.** A big name with no pain is still dead, and it eats the most time.
- **Never disqualifying.** A pipeline nobody ever removes deals from is a fantasy, not a forecast.
- **Confusing a champion with a buyer.** A friendly user who loves it but can't pay is a path to power, not power itself.

## Escalate to your QC advisor when

- The honest triage leaves almost nothing real. That's an ICP, motion, or top-of-funnel problem, above this pack, and the advisor should hear it now, not at quarter's end.
- A single large deal is the whole forecast. Concentration risk is a strategy conversation.
- The founder keeps overriding the triage and working dead deals. That's a coaching conversation a human should have.

## Your next 30 minutes

- [ ] List every live deal.
- [ ] Score each against pain, power, urgency, next step. Use their actual words as evidence.
- [ ] For each, write the one gap and the one dated next move.
- [ ] Set a next step on anything at-risk, today.
- [ ] Update the live-deals table in the brief, and decide what to walk away from.

---
<sub>QC Sales Coaching Pack · [QC Growth](https://qcgrowth.com). When a framework can't make the call, that's what your QC advisor is for.</sub>
