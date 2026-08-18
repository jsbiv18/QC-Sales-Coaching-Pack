---
name: sales-call-review
description: Turn a founder-led sales or discovery call transcript into an honest coaching review: what the prospect actually signaled, what the founder did well, the specific moments to change, the objections to prep for, and the one next step that decides the deal. Appends the recurring pattern to coaching-log.md so patterns across calls become visible. Use after any founder-led call (discovery, demo, follow-up) with a transcript or notes. For the founder selling their own product, not a sales team. Reads sales-brief.md and coaching-log.md first.
---

# Review your sales call (the coaching pass)

> A recording is not feedback. Most founders replay a call in their head, remember the parts that felt good, and learn nothing. Paste the transcript and get the honest version: what the prospect actually told you, where you lost the thread, and the one move that decides whether this deal is real.

**Use this when:** the founder just ran a founder-led call and has the transcript or decent notes, or keeps having calls that feel positive and go nowhere.

## The core idea

The founder was in the call, which is exactly why they can't see it clearly. They were talking, managing nerves, and hearing what they wanted to hear. The transcript is ground truth. This reads it against what a good founder-led call should do and gives a coach's review: honest, specific, tied to real moments, pointed at the next call, not a grade on this one.

Reads `docs/qc-sales/sales-brief.md` (who this prospect should be, the positioning, the pain killed) and `docs/qc-sales/coaching-log.md` (what this founder keeps getting wrong). Then it turns the call into three things: a better next call, validated facts for the brief, and an updated pattern in the log.

## How to run this (for the agent)

1. Read the sales brief and the coaching log if they exist. Do not require them. If there is no `docs/qc-sales/sales-brief.md` yet (for example this skill is being run on its own, before `00-sales-setup`), do not stop or ask the founder to go create one. Just ask for the couple of things you need inline (product, who adopts vs who buys, and the deal in question) and continue. This pack works on its own.
2. Ask the founder to paste the transcript or notes, plus one line of context: the stage (discovery, demo, follow-up) and who was on the call (role, company).
3. Produce the review in the structure below. Be specific and quote the transcript. Never give vague notes like "build more rapport." Point at the exact moment and the exact better line.
4. Be honest, not kind. A founder who leaves feeling good and learns nothing is worse off. Concede what genuinely went well, then be direct about what didn't.
5. Append the recurring pattern to the coaching log, and write validated facts back to the brief.

## The review structure

**1. The one-line state of the deal.** Real, maybe, or dead. Say it plainly. A warm call with no next step is not a live deal.

**2. What the prospect actually signaled.** Their words, not the founder's hopes:
- Did they describe a painful problem in their own words? Quote it. If not, the founder was selling to someone not in pain.
- Urgency: a reason to act now, or just "interesting"?
- Who owns the decision, and were they on the call?
- Any budget or buying-process signal.

**3. What the founder did well.** Two or three specific moments, quoted. Real ones only, so they keep doing them.

**4. What to change (the coaching).** The heart of it. Find the moments and give the better move. Look hard for:
- **Talked more than listened.** More than about 40 percent of a discovery call spoken by the founder means they pitched instead of discovered. Show where.
- **Demoed before understanding the pain.** Feature talk before they named a problem means selling to a blank.
- **Pitched features, not their outcome.** Quote where the founder said what it does instead of what it does for them.
- **Happy ears.** Where "cool" got heard as intent.
- **Missed a signal.** A pain or objection raised and talked past.
- **No clear next step.** The big one, see below.

**5. Objections, and how to handle them next time.** Every hesitation raised, with a specific, honest response for the next call. No spin. For a full playbook, point to `objection-handling`.

**6. The next step.** Did they leave with a specific, scheduled next step? If not, that is the number one fix, ahead of everything else. Founder-led deals die in the gap between "sounds great" and "let's find time." Hand off to `sales-followup` to draft the exact message that sets it.

## The decision tree

```
Did the prospect describe a real, painful problem in their own words?
├─ NO  → this was a conversation, not a sales call. Requalify before spending another hour.
│         The fix is upstream: who is this really for, and are we talking to them?
└─ YES → did the founder leave with a specific, scheduled next step?
         ├─ NO  → that is the whole problem. Run sales-followup today.
         └─ YES → is the person who owns the decision the one they talked to?
                  ├─ NO → the next step is access to the buyer, not another demo.
                  └─ YES → this is real. Run deal-qualification and drive it.
```

## Mistakes that look reasonable

- **Grading the call instead of improving the next one.** "Here is the exact question to ask next time" beats a score.
- **Being kind.** Softening to protect feelings robs the founder of the fix.
- **Coaching to a generic sales playbook.** The founder's edge is deep product and problem knowledge. Coach them to use it, not to sound like an SDR.
- **Treating one good call as a pattern.** One warm call is not traction.

## Update the coaching log

This is what makes the pack feel like a coach who was there last week. After the review, open `docs/qc-sales/coaching-log.md` and:
- Under **Recurring patterns**, add or reinforce the main thing to fix. If it's the second or third time, say so explicitly in the next review: "third call running, this is the pattern to break."
- Under **Wins to keep**, log what genuinely worked.
- Under **Open objections to prep**, add any new objection in the prospect's words.

## Feed the brief

Every call is a source of validated facts. Update `docs/qc-sales/sales-brief.md`:
- Real objections, in the prospect's words.
- The language they used for the pain (positioning gold).
- Whether they matched the ICP, or revealed it's off.
- Flip any `[assumption]` the call validated to `[validated]`.

## Escalate to your QC advisor when

- The same pattern is now in the log three or more times and isn't moving. Coaching-by-skill has done its job; this needs a live session. Say so plainly.
- The review keeps concluding "not a real deal" across most of the pipeline. That's an ICP or motion problem, above this pack. Route it to the advisor.
- A big deal is genuinely in play and the next move is high-stakes (pricing, a competitive bake-off, a security review). Flag for advisor involvement.

## Your next 30 minutes

- [ ] Paste the transcript and one line of context.
- [ ] Read the state-of-the-deal line first, and be honest about it.
- [ ] Do the single next-step fix today, before anything else.
- [ ] Run sales-followup to send the next step.
- [ ] Add the real objections and their exact words to the brief, and the pattern to the log.

---
<sub>QC Sales Coaching Pack · [QC Growth](https://qcgrowth.com). When a framework can't make the call, that's what your QC advisor is for.</sub>
