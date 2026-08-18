# QC Sales Coaching Pack

**A sales coach for your founders that works when we're not in the room.**

This is a set of installable skills that run inside the founder's own AI agent (Claude Code, Cursor, Codex, Windsurf, ChatGPT, any tool that supports the Agent Skills spec). It encodes the QC founder-led sales method so a founder gets coached on every call, prep, follow-up, and deal, between the sessions they have with their QC advisor.

It does not replace the advisor. It handles the **knowable** calls (call structure, objection surfacing, next-step discipline, deal qualification) so the advisor's time is spent on the **unknowable** ones (judgment, strategy, the deal that's really about the founder's confidence). Every skill knows when to stop and say "take this to your QC advisor."

---

## The three-layer model

This pack is the **House layer**: QC's reusable method, identical across every client.

1. **Public (gtmcofounder.com).** Free, open-source GTM skills. Top of funnel. Not this pack.
2. **QC House Pack (this repo).** QC's productized method. Built once, deployed to every engagement.
3. **Client-bespoke pack.** This pack, tuned to one founder's ICP, positioning, pricing, and objections via their `sales-brief.md`. That's what `00-sales-setup` produces, and it's what makes the coaching about *their* business, not a textbook's.

You deploy the House layer as-is, run `00-sales-setup` with the founder once, and from then on every skill reads their brief first.

---

## What's in the pack

| Skill | Reach for it when the founder… |
|-------|--------------------------------|
| **00-sales-setup** | Is starting with the pack. Writes `sales-brief.md` and `coaching-log.md`, the memory every other skill reads first. Do this once. |
| **sales-call-prep** | Has a call booked and wants to walk in with a goal, three questions, a target next step, and the objections ready. |
| **sales-call-review** | Just ran a call and has the transcript or notes. Turns it into an honest coaching review, not a replay. |
| **sales-followup** | Needs to send the follow-up that sets a next step, or a stalled deal has gone quiet. |
| **objection-handling** | Keeps hitting "let me think about it," "no budget," "we'll build it," and folds or spins instead of surfacing it. |
| **deal-qualification** | Has a pipeline full of "warm" deals and can't tell which are real or what the single next move is. |
| **crm-sync** | Runs HubSpot or Attio. Reads the live pipeline into the coaching and writes call summaries, objections, and next steps back, every write gated by the founder's approval. |

## The coaching loop

```
        00-sales-setup  (once)
               │
   ┌───────────┼───────────────────────────┐
   ▼           ▼                             ▼
sales-call-prep → [call] → sales-call-review → sales-followup
                              │                     │
                    objection-handling      deal-qualification
                              │                     │
                              └──── coaching-log.md ─┘
                        (patterns across calls, so it remembers)
```

`coaching-log.md` is what makes it feel like a coach who was there last week. `sales-call-review` appends the recurring pattern from each call, so by the third call it can say "you've demoed before discovery three calls running, that's the pattern to break," which is exactly what an advisor who sat in would say.

**`crm-sync` is optional but changes the game.** If the founder runs HubSpot or Attio, set it up in `00-sales-setup` and the pack stops reading a hand-typed deal table and starts reading the real pipeline, then writes coaching output back (call summaries, objections, next steps), so it also does the CRM admin founders avoid. Every write is shown as a diff and approved first. Without a CRM, the pack runs fine on the manual brief.

---

## Install

In the founder's AI coding agent, tell it:

> Install the skills from this repo and run 00-sales-setup with me.

If the agent can't fetch a repo from a link, clone it first, then give it the same instruction. For Claude Code, the skills live in `~/.claude/skills/`; copy the folders from `skills/` there. For the Claude apps, upload each skill folder under **Customize → Skills**. In a plain chat tool (ChatGPT, Claude), open a skill, paste the text, and say "apply this to my product."

**Testing a single skill on its own?** You don't need to run `00-sales-setup` first. Every skill reads `docs/qc-sales/sales-brief.md` if it exists, but works fine without it and will just ask you what it needs. If your agent complains it can't find that file, tell it to skip it and continue. Running `00-sales-setup` first just makes the coaching more specific.

---

## How QC uses this (internal)

- **Deploy per engagement.** Fork or copy the House pack into a private repo scoped to the client. Run `00-sales-setup` on the kickoff call so the brief is real from day one.
- **Tune, don't rewrite.** The bespoke layer is the `sales-brief.md`, not new skills. Keep the method identical so improvements to the House pack flow to every client.
- **Escalation is a feature.** Each skill flags when a call is above its pay grade and routes the founder back to their advisor. That's how the pack protects the relationship instead of replacing it.
- **Own the maintenance.** Packs rot. One person owns versioning and a quarterly refresh (see CHANGELOG). A stale pack is worse than a Notion doc.
- **Never overclaim.** Internally this is leverage on the QC method. Externally, it is "your QC sales coach, on call in the tool you already use," not "we replaced your sales hire."

## The method it encodes

Founder-led sales for developer and AI tools: market to the developer who adopts, sell to the buyer who pays, surface objections instead of spinning them, and never leave a call without a scheduled next step. Grounded in QC's operating experience (founding-AE and dev-tool GTM advisory) and sharpened by Adam Frankl (*The Developer-Facing Startup*) and Jakub Czakon (*markepear.dev*).

---

<sub>QC Sales Coaching Pack · Built by [QC Growth](https://qcgrowth.com). When a framework can't make the call, that's what your QC advisor is for.</sub>
