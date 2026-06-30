---
name: call-scorer
description: >
  Score candidate interview and screening calls against a hiring rubric, using meeting transcripts
  and notes. Use this skill whenever the user wants to "score the interview", "give feedback on a
  candidate call", "how did that candidate do", "rate the candidates from this week's interviews",
  "pull my interview notes and score them", or wants structured feedback on a recorded conversation
  with a candidate. Connects to Granola via MCP to read transcripts and notes, then scores against
  the rubric-builder framework. Always score against an explicit rubric — build one first if none
  exists.
---

# Interview Call Scorer

## What This Skill Does

Reads candidate interview/screening calls (transcripts + notes from **Granola via MCP**) and produces
a **structured score and written feedback per candidate**, mapped to the hiring rubric. The output
tells the user: how the candidate scored on each dimension, *with evidence quoted or paraphrased from
the actual call*, and a clear advance / hold / pass recommendation.

This turns a pile of recorded interviews into a ranked, evidence-backed shortlist.

---

## Prerequisites & Limitations (Read First)

This skill depends on **Granola MCP**. Know these constraints before relying on it:

1. **Transcript access requires a Granola Business plan or higher.** On the free/Basic tier, the MCP
   only exposes the last 30 days of notes and *no transcripts.* For real scoring you want
   transcripts — flag this to the user if scoring seems thin.
2. **Granola MCP only sees the authorizing user's private "My notes" space — never Team-space
   folders.** If interviews live in a shared Team space, each interviewer must connect their own
   Granola, or scoring will come back empty. Surface this if a search returns nothing.
3. **A rubric must exist.** Score against an explicit rubric (use the `rubric-builder` skill). Never
   invent scoring criteria silently — that just launders the scorer's bias.

If Granola isn't connected, say so and suggest enabling it. Don't fabricate call content.

---

## Process

1. **Confirm the rubric.** Ask which rubric to score against, or build one with `rubric-builder`. The
   5 default dimensions: Quality of Questions Asked, Evidence of Slope, Self-Awareness, Culture Fit &
   Values, Real Work Output.
2. **Pull the call(s) from Granola.** Use the MCP to find the relevant meeting(s) by candidate name,
   date, or title. Prefer the natural-language query tool for open-ended retrieval; pull the full
   transcript when available for direct evidence.
3. **Score each dimension 1–5**, anchored to the rubric. For every score, cite specific evidence —
   what the candidate actually said or did. No evidence = lower confidence, say so.
4. **Compute the weighted total** using the rubric's weights.
5. **Check hard gates** — any dimension where a 1 is an automatic no.
6. **Write the recommendation:** advance / hold / pass, with the reasoning in one tight paragraph.
7. **If scoring multiple candidates,** produce a ranked comparison table at the end.

---

## How to Score Well

- **Evidence over impression.** Every score points at something concrete from the call. "Scored 5 on
  Quality of Questions — asked how the company thinks about retention vs. acquisition, then pushed on
  the growth model" beats "great questions."
- **Watch the question quality signal closely.** What the candidate *asked* is often the cleanest
  read on how they think. Pull their questions out explicitly.
- **Distinguish slope from pedigree.** Reward evidence of fast self-driven learning over a glossy
  résumé. Flag candidates who only replay a prior company's playbook.
- **Score culture fit separately and against the company's real values** — never fold it into general
  competence.
- **Be honest about missing signal.** If the call never surfaced work output, don't guess — note the
  gap and recommend a work trial or take-home.
- **Don't inflate.** A 3 is "solid, would do the job." Reserve 5 for genuinely exceptional. If
  everyone's a 5, the rubric is useless.

---

## Output Format

ALWAYS use this structure (per candidate):

```
# Candidate Scorecard: [Name]
**Role:** [title] · **Call:** [date / type] · **Source:** Granola

| Dimension | Weight | Score (1–5) | Evidence |
|---|---|---|---|
| Quality of Questions | 15% | X | [what they asked / didn't] |
| Evidence of Slope | 20% | X | [learning signal from the call] |
| Self-Awareness | 15% | X | [how they handled pushback] |
| Culture Fit & Values | 15% | X | [values evidence] |
| Real Work Output | 35% | X | [work signal, or note the gap] |
| **Weighted Total** | 100% | **X.X / 5** | |

**Hard gates:** [pass / triggered — which]
**Recommendation:** [Advance / Hold / Pass]
**Why:** [one tight paragraph — the decisive factors]
**What to probe next round:** [gaps the call didn't resolve]
```

For multiple candidates, end with:

```
## Ranked Shortlist
| Rank | Candidate | Score | Recommendation | One-line read |
|---|---|---|---|---|
```

---

## Scorer Failure Checklist

A scorecard FAILS if it:
- ❌ Scores without citing evidence from the actual call
- ❌ Invents criteria instead of scoring against the explicit rubric
- ❌ Inflates scores (everyone's a 4–5, no discrimination)
- ❌ Folds culture fit into general competence
- ❌ Rewards pedigree over demonstrated slope
- ❌ Guesses at dimensions the call never surfaced instead of flagging the gap
- ❌ Gives a recommendation that doesn't follow from the scores and gates
