---
name: rubric-builder
description: >
  Build structured, weighted interview scoring rubrics for any role. Use this skill whenever the
  user wants to "build a rubric", "create a scorecard", "set up interview scoring", "how should we
  evaluate candidates", "what should we score on", or is designing a hiring loop and needs a way to
  rate candidates consistently. Also trigger when the user wants to standardize how interviewers
  grade, reduce hiring bias, or align a panel on what "good" looks like. The rubric this skill
  produces is the backbone the call-scorer and cv-screener skills score against — build it first.
---

# Interview Rubric Builder

## What This Skill Does

Produces a **weighted, behaviorally-anchored scoring rubric** for a specific role. The output is a
rubric a whole interview panel can use to score candidates consistently, on a 1–5 scale per
dimension, with concrete descriptions of what each score looks like. No vague "rate culture fit
1–10" — every score level is anchored to observable behavior.

The goal is **signal, not vibes.** A good rubric forces interviewers to point at evidence.

---

## The Method: Behaviorally-Anchored Rating Scales (BARS)

The best-validated approach to interview scoring. Each dimension gets:
- A clear definition of what's being measured
- A weight (how much it counts toward the total)
- Anchored descriptions for scores 1, 3, and 5 (what each looks like in practice)
- 1–2 probing questions an interviewer can ask to surface the signal

BARS beats numeric-only scales because it reduces interviewer drift — two people watching the same
interview land on similar scores because they're matching behavior to anchors, not guessing.

---

## The 5 Core Dimensions (Always Include These)

These five are the default backbone for any role. Adjust weights by role, but include all five
unless the user explicitly cuts one. Each is drawn from how the best operators actually hire.

### Dimension 1: Quality of Questions Asked

**What it measures:** How the candidate thinks, revealed by what they ask. The best candidates ask
"why," not just "what." Are they trying to understand the customer, the market, the growth model? Or
are they asking about comp and title? The depth and direction of their questions is one of the
cleanest signals of how they think.

**Anchors:**
- **1 — Surface:** Asks only about logistics, comp, title, perks. No questions about the business,
  product, or customer.
- **3 — Engaged:** Asks good clarifying questions about the role and team. Shows interest but stays
  inside the frame you gave them.
- **5 — Probing:** Asks "why" questions that reframe the problem. Digs into the customer, the market,
  the growth model, the strategy. Their questions teach *you* something.

**Probe:** Leave deliberate space near the end. The questions they choose to ask when handed an open
floor are the data.

---

### Dimension 2: Evidence of Slope

**What it measures:** The *rate* at which someone learns and improves — not where they are now, but
how fast they climb. Look for people who've shipped something on their own, iterated on a side
project, or shown measurable improvement over a short window.

This matters more than pedigree. As Elena Verna has emphasized: if someone comes in from the outside
and just slaps their previous company's growth model onto your product, it's most likely a near-total
failure. You want someone who adapts fast, not someone who replays a playbook.

**Anchors:**
- **1 — Flat:** Replays past playbooks. Describes success entirely in terms of what worked at a prior
  company. No evidence of self-driven learning or iteration.
- **3 — Rising:** Has grown clearly in past roles. Can describe how they got better at something, with
  a rough sense of the curve.
- **5 — Steep:** Visible, fast self-improvement. Shipped/iterated on their own. Can point to
  measurable improvement over a short window. Adapts frameworks to context instead of copy-pasting.

**Probe:** "Tell me about something you taught yourself in the last 6 months." "What did you ship that
nobody asked you to ship?"

---

### Dimension 3: Self-Awareness

**What it measures:** Whether they can explain *why* they made the decisions they made, name their own
weaknesses unprompted, and adapt on the fly when challenged.

Jason Fried at 37signals does this by having candidates present their work trial and then poking holes
in it. What he's watching for: can they defend and adapt, or do they go deer-in-the-headlights? As he
put it, some people deliver really good work and then freeze the moment you ask them a question about
it.

**Anchors:**
- **1 — Brittle:** Can't explain their reasoning. Defensive or frozen when challenged. Can't name a
  real weakness (or names a fake one like "I work too hard").
- **3 — Reflective:** Explains most decisions clearly. Names genuine weaknesses when asked. Holds up
  okay under light pushback.
- **5 — Anti-fragile:** Explains the *why* behind decisions crisply. Names weaknesses unprompted and
  describes how others perceive them. Gets *better* under pushback — updates in real time without
  caving or digging in.

**Probe:** Present their work (or work trial) back to them and poke holes. Watch whether they defend
with reasoning, adapt with new information, or freeze.

---

### Dimension 4: Culture Fit & Values Alignment

**What it measures:** Alignment with how your company actually operates — scored *separately* from
skills, on purpose. At PostHog, James Hawkins scores culture fit as its own line item, not folded
into competence. For a small company this is even more critical: one misaligned hire can poison the
well for everyone else.

**Anchors:**
- **1 — Misaligned:** Values or working style clash with the team's. Would create friction.
- **3 — Compatible:** No red flags. Would fit fine, no strong pull either way.
- **5 — Additive:** Embodies the company's actual values. Raises the bar for everyone around them.

**Probe:** Define 2–3 of *your* real values first (not generic ones), then ask for specific past
behavior that maps to each. "Tell me about a time you [lived value X]."

> **Note:** Customize this dimension's anchors to the company's *actual* values before use. Generic
> culture-fit scoring is worse than none — it just launders bias. If the user hasn't given you their
> real values, ask for them.

---

### Dimension 5: Real Work Output (Highest Weight)

**What it measures:** Can they actually do the job? This is the single most predictive signal, and it
should carry the most weight. Interviews are a weak proxy; *work* is the real thing.

If you can give candidates a paid work trial — even 3–5 days — you'll get 10x the signal of any
interview. Linear pays $600/day for work trials regardless of seniority, and many thoughtful
applicants see this as a positive because they get to evaluate the team too. Gumroad takes it
furthest, paying candidates their full hourly rate for 4–6 weeks; as Sahil Lavingia put it, it's so
hard to know a priori if someone can do the job that you just pay them to do it.

**Anchors:**
- **1 — Unproven / weak:** No work sample, or the sample doesn't meet the bar. Talks well but can't
  show the work.
- **3 — Solid:** Work sample meets the bar. Competent, would do the job.
- **5 — Exceptional:** Work sample is clearly top-tier. During a trial, integrated fast, raised
  questions you hadn't considered, shipped real value.

**Probe:** A paid work trial is the gold standard — recommend one wherever feasible. If not possible, a
take-home tied to a *real* problem you're facing, reviewed against this anchor.

---

## How to Build the Rubric

1. **Get the role context.** Title, seniority, team size, what success looks like in 6 months. Ask if
   you don't have it.
2. **Start with the 5 core dimensions.** Add role-specific ones only if there's a genuine gap (e.g.,
   "Technical depth" for an engineer, "Marketing fluency" for the Flint Growth Strategist role).
3. **Assign weights.** Default starting point below. Adjust to the role and tell the user why.
4. **Anchor every dimension** at scores 1, 3, 5. Always behavioral, always observable.
5. **Customize culture fit** to the company's real values — never ship generic anchors here.
6. **Add the probing questions** so interviewers know how to surface each signal.
7. **Set a decision threshold** and flag any dimension that should be a hard gate (a 1 = auto-no
   regardless of total).

### Default Weights (Adjust Per Role)

| Dimension | Default Weight | When to raise it |
|---|---|---|
| Real Work Output | 35% | Almost always the heaviest. Raise further for ICs. |
| Evidence of Slope | 20% | Early-stage, fast-changing roles. |
| Quality of Questions | 15% | Strategic / customer-facing / senior roles. |
| Self-Awareness | 15% | Leadership, design, anything requiring judgment under pushback. |
| Culture Fit & Values | 15% | Small teams where one bad hire poisons the well — raise to 20%+. |

Weights must sum to 100%. State the final weights and your reasoning.

---

## Output Format

ALWAYS produce the rubric in this structure:

```
# Interview Rubric: [Role Title]
**Role context:** [seniority, team, what success looks like]
**Decision threshold:** [e.g., weighted score ≥ 4.0 to advance]
**Hard gates:** [any dimension where a score of 1 = automatic no]

## Scoring Dimensions

### [N]. [Dimension Name] — Weight: [X]%
**Measures:** [one line]
| Score | What it looks like |
|---|---|
| 1 | [anchor] |
| 3 | [anchor] |
| 5 | [anchor] |
**Probe:** [question(s) to surface the signal]

[repeat for each dimension]

## Scoring Sheet (per candidate)
| Dimension | Weight | Score (1–5) | Weighted | Evidence |
|---|---|---|---|---|
| ... | ... | | | |
| **Total** | 100% | | **/5** | |

## How to Use This
[2–3 lines: each interviewer scores independently, then debrief, cite evidence, watch hard gates]
```

---

## Rubric Failure Checklist

A rubric FAILS if it:
- ❌ Uses unanchored numeric scales ("rate 1–10") with no description of what each number means
- ❌ Has generic culture-fit anchors not tied to the company's real values
- ❌ Folds "can they do the job" into a soft competence score instead of weighting work output highest
- ❌ Rewards pedigree over slope (where they've been vs. how fast they climb)
- ❌ Has no probing questions, leaving interviewers to guess how to surface each signal
- ❌ Weights that don't sum to 100%, or weights with no stated reasoning
- ❌ No decision threshold and no hard gates — every dimension treated as equally fungible
