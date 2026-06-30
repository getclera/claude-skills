---
name: cv-screener
description: >
  Screen and rank candidate CVs/resumes against a role, producing a scored shortlist with reasons.
  Use this skill whenever the user uploads resumes and a job description, or says "screen these
  candidates", "rank these CVs", "who should we interview", "filter these applicants", "go through
  this batch of resumes". Also trigger for shortlisting from a candidate spreadsheet or list. Scores
  against the role's must-haves, nice-to-haves, and red flags, and surfaces signal beyond keywords.
---

# CV Screener & Ranker

## What This Skill Does

Takes a batch of CVs + a role definition and returns a **ranked shortlist** — each candidate scored,
with a one-line reason and any red flags. The point is to get the user to a confident "interview
these N" decision fast, while flagging the close calls a human should look at.

This is a *first-pass filter*, not a final decision. It surfaces signal; the human decides.

---

## Process

1. **Get the role bar.** Pull must-haves, nice-to-haves, and red flags from the JD or rubric. If
   none provided, ask for the 3–5 things that genuinely matter for this role.
2. **Read each CV against the bar.** Score must-haves (pass/partial/miss), note nice-to-haves, flag
   red flags.
3. **Look past keywords for real signal:** evidence of *slope* (shipped things, fast growth, self-
   driven projects), trajectory, and whether their experience maps to *this* problem vs. a generic
   match.
4. **Rank** into tiers: Strong yes / Worth a look / Likely no — with reasoning.
5. **Flag close calls** explicitly so the human reviews them rather than trusting the cut.

---

## How to Screen Well

- **Slope over pedigree.** A candidate who shipped a side project and grew fast often beats a glossier
  résumé. Reward evidence of self-driven improvement.
- **Map to the actual problem.** "5 years in X" matters less than whether their experience fits *this*
  role's real challenge. Note when a strong-looking CV is a weak fit and vice versa.
- **Be honest about gaps.** Don't pad a thin CV to fill a shortlist. A short honest shortlist beats a
  padded one.
- **Surface, don't bury, red flags.** Job-hopping with no narrative, unexplained gaps, claims that
  don't add up — name them. The human decides if they matter.
- **Never auto-reject on proxies** that correlate with protected characteristics (school prestige,
  name, gaps that may be caregiving). Score on demonstrated capability.

---

## Output Format

```
# CV Screen: [Role] — [N] candidates

## 🟢 Strong Yes
| Candidate | Fit | Why | Watch |
|---|---|---|---|
| [name] | [score] | [one line] | [any flag] |

## 🟡 Worth a Look
[same table — the close calls; note what to verify in a screen]

## 🔴 Likely No
| Candidate | Why not |
|---|---|

## Notes
[Anything the human should know — e.g., "3 candidates were borderline on X; I'd screen them rather
than cut." Or "the strongest CV on paper is a weak fit for this specific problem."]
```

---

## Screener Failure Checklist

A screen FAILS if it:
- ❌ Ranks on keyword matching instead of real fit to the role's actual problem
- ❌ Rewards pedigree over demonstrated slope
- ❌ Pads the shortlist to hit a number instead of being honest about a thin field
- ❌ Hides red flags or close calls instead of surfacing them for human review
- ❌ Auto-rejects on proxies for protected characteristics
- ❌ Gives scores with no reasoning the human can sanity-check
