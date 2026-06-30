---
name: application-post-mortem
description: >
  Analyze why a job application or interview didn't work out, and turn it into calibration for the
  next one. Use this skill whenever someone says "I got rejected", "I didn't get the job", "why am I
  getting ghosted", "what went wrong with my application", "help me figure out why I keep getting
  rejected", or wants to learn from a failed process. Reviews the role, the candidate's materials, and
  what happened — including interview transcripts if they have them (via a note-taker MCP or pasted) —
  and gives an honest read on the likely cause plus what to change. Gather everything about the
  process first.
---

# Application Post-Mortem

## What This Skill Does

Turns a rejection or a ghosting into **useful calibration** instead of demoralization. It reviews
everything about the failed process — the role, the candidate's materials, how the interviews went —
and gives an honest, specific read on the *likely* reasons, then a concrete list of what to change for
the next one.

The bar is honest and useful. Not "their loss!" cheerleading, and not brutal either — a clear-eyed
read a good mentor would give, aimed at making the next attempt better.

---

## Gather Maximum Context First — Including Transcripts

The more of the actual process you can see, the better the diagnosis. Collect:

1. **The role and company** (required) — ideally the JD.
2. **The candidate's materials** (required) — the resume/cover letter they used, tailored or not.
3. **What actually happened** — at what stage did it end? Applied and ghosted? Rejected after a
   screen? After final round? Any feedback they got, however vague.
4. **Interview transcripts, if they have them** — this is the richest signal. Handle it like this:
   - Ask: **"Do you use a note-taker that recorded your interviews?"** (Granola, Fathom, Otter,
     Fireflies, etc.)
   - **If yes and there's an MCP for it** → offer to connect it: Granola, Fathom, Otter, and Fireflies
     all have Claude MCP connectors. Walk them through connecting so you can pull the transcript.
   - **If no MCP, or they'd rather not connect** → ask them to paste the transcript or their notes.
   - **If they have nothing recorded** → work from their recollection; ask them to walk through how
     each interview felt and what was asked.
5. **Their own read** — what they think went wrong (often partly right, sometimes the blind spot is
   the issue).

Push for the transcript or detailed recollection — a post-mortem on "I applied and got rejected" with
no detail can only be generic.

---

## Process

1. **Map the funnel.** Where it ended tells you a lot: ghosted post-application points at resume/
   fit/keyword issues; rejected post-screen points at comp/logistics/basic fit; rejected post-final
   points at something in the interview performance or a stronger competitor.
2. **Review materials against the role** — was the resume actually tailored? Did it surface the right
   fit? Any red flags?
3. **Analyze the interview** (from transcript/recollection) — answer quality, missed signals, where
   they may have lost the room, questions they fumbled.
4. **Diagnose honestly** — the likely cause(s), flagged by confidence. Often it's not one thing.
   Distinguish what they can control (materials, prep, answers) from what they can't (a stronger
   internal candidate, budget pulled, timing).
5. **Prescribe specifics** — exactly what to change next time. Concrete, not "be more confident."

---

## Output Format

```
# Post-Mortem: [Role] at [Company]

## Where It Ended (and what that suggests)
[The funnel stage and what it typically points to.]

## Likely Causes (honest, by confidence)
[The probable reasons, flagged [likely] / [possible]. Separate what they controlled from what they
didn't — so they don't over-blame themselves for a pulled budget, or under-examine a fixable gap.]

## What the Materials/Interview Showed
[Specific observations from the resume and transcript/recollection — the actual evidence.]

## What to Change Next Time
[Concrete, specific fixes. Resume changes, prep changes, answer changes — actionable, not platitudes.]

## What to Keep Doing
[What was actually working — so they don't throw out the good with the bad.]
```

---

## Note-Taker MCP Setup (if pulling transcripts)

Granola, Fathom, Otter, and Fireflies all have Claude MCP connectors. To connect one: Customize →
Connectors → find it (or add as custom connector) → authenticate via OAuth → enable it in the chat via
the "+" menu. If the candidate's note-taker has no MCP or they prefer not to connect, pasting the
transcript works just as well. Never require the MCP — it's the convenient path, not the only one.

---

## Quality Bar / Failure Checklist

This FAILS if it:
- ❌ Gives generic "keep trying!" encouragement instead of a real diagnosis
- ❌ Is brutal without being useful — honesty should aim at improvement, not just sting
- ❌ Blames only things the candidate can't control (or only things they can) instead of separating them
- ❌ Diagnoses on thin input without pushing for the transcript or detailed recollection
- ❌ Prescribes platitudes ("be more confident") instead of specific changes
- ❌ Forces an MCP connection when pasting a transcript would do
