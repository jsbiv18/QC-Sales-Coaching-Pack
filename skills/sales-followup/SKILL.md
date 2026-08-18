---
name: sales-followup
description: Write the follow-up that actually moves a founder-led deal forward after a call: restate the prospect's problem in their words, lock a specific next step, and handle the stalls ("let me think about it", "send me some info", "not right now") without going cold or chasing. Use right after a sales or discovery call, or when a deal has stalled and the founder doesn't know what to send. For the founder selling their own product, not a sales team. Reads sales-brief.md and any sales-call-review output first.
---

# Follow up so the deal doesn't die

> Most founder-led deals don't die in the call. They die in the silence after it. The prospect said "this is great," the founder sent "let me know if you have questions," and now it's three weeks later. The follow-up is not admin. It's where the deal is won or lost.

**Use this when:** the founder just finished a call, or a deal has gone quiet and they can't tell what to send that isn't "just checking in."

## The core idea

A good follow-up does one job: make it easy for the prospect to take the next step, and hard to quietly forget you. Reflect their problem back in their own words so they feel understood, name the specific next step with a time, and give one low-friction thing to say yes to. "Let me know" is not a next step. It's handing the deal to their inbox to bury.

Reads `docs/qc-sales/sales-brief.md` and, if present, the output of `sales-call-review` (the objections and the next step it flagged), so the follow-up is grounded in what actually happened.

## How to run this (for the agent)

1. Read the brief and any call-review output if they exist. Do not require them. If there is no `docs/qc-sales/sales-brief.md` yet (for example this skill is being run on its own, before `00-sales-setup`), do not stop or ask the founder to go create one. Just ask for the couple of things you need inline (product, the prospect, and what happened on the call) and continue. This pack works on its own.
2. Ask for context if not known: what the prospect said the problem was (their words), what was agreed, and whether a next step was set.
3. Write the follow-up in the structure below. Use their language, not marketing language. Short. A founder wrote this, not a sequencer.
4. If there was no clear next step, the follow-up's whole job is to set one. Propose a specific time and action.
5. Handle whatever stall they gave with the responses below.

## The follow-up structure

Four parts, short:
1. **Their problem, in their words.** One line that proves you listened. Quote them if you can.
2. **What was agreed, or the value.** The specific thing that would change for them.
3. **The next step, with a time.** "Does Thursday at 2 work to run a pilot on your repo?" not "let me know."
4. **One low-friction action.** A pilot, a shared doc, an intro to one teammate. Something they can say yes to in a sentence.

## Handling the common stalls

- **"Let me think about it."** Almost always an unspoken objection or no real urgency. Don't "circle back." Surface it: "Totally fair. When founders say that, it's usually one of two things: it's not a priority right now, or something about it doesn't fit. Which is closer?"
- **"Send me some info."** Often a polite exit. Send one specific thing tied to their problem, with a next step attached, not a brochure.
- **"We're not ready / too early."** Pin down what "ready" looks like and when, so you know if it's real or a soft no. Ask what would need to be true.
- **"No budget."** Budget appears for real pain. If there's none, the pain wasn't big enough, go back to discovery. If the pain is real, find who owns the budget.

For anything beyond a one-line stall, hand to `objection-handling` for the full response.

## The decision tree

```
Did the founder leave the call with a scheduled next step?
├─ YES → send the four-part follow-up today, confirming it. Don't overthink it.
└─ NO  → the follow-up must create one. Propose a specific time and a specific action.
         Did they give a stall ("let me think about it", etc.)?
         ├─ YES → address the stall directly (above). Never send "just checking in".
         └─ NO  → they simply haven't replied. New angle or a graceful close, never a nag.
```

## Mistakes that look reasonable

- **"Just following up."** Adds nothing, asks for nothing, reads as a nag. Every touch needs a reason and an ask.
- **Recapping features instead of their outcome.** They need to remember why it mattered to them, not the feature list.
- **No specific ask.** "Let me know your thoughts" moves nothing.
- **Waiting for them to come back.** In founder-led sales, if the founder isn't driving it, it's dead.
- **Discounting to force a yes.** A price cut doesn't fix a missing reason to buy. It teaches them to wait.

## The cadence

If they go quiet, space follow-ups out (a few days, then a week), each with a new specific reason (a relevant update, a real question, a resource tied to their problem), not a repeated nudge. After three or four with no reply, send a graceful close ("I'll stop chasing, the door's open if this becomes a priority"). A clean close often gets a reply a nag never would.

## Escalate to your QC advisor when

- The founder wants to discount to save the deal. That's a pricing and value conversation for the advisor, not a follow-up. Flag it before they send a number.
- The deal is large and the follow-up needs to reach a senior buyer the founder hasn't met. The advisor may have a warmer path or a better frame.

## Feed the brief

Log the real objection or stall and the exact language used, and flip any `[assumption]` the call confirmed to `[validated]`.

## Your next 30 minutes

- [ ] Write the four-part follow-up and send it today, while the call is fresh.
- [ ] If no next step was set, propose a specific time and action in it.
- [ ] If they stalled, address the real objection, don't "circle back."
- [ ] Log the objection and their words in the brief.

---
<sub>QC Sales Coaching Pack · [QC Growth](https://qcgrowth.com). When a framework can't make the call, that's what your QC advisor is for.</sub>
