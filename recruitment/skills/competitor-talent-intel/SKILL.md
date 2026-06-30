---
name: competitor-talent-intel
description: >
  Analyze competitors' hiring activity to inform sourcing and talent strategy. Use this skill
  whenever the user asks "who is [company] hiring", "what roles are competitors posting", "talent
  intelligence on [company]", "where can we poach from", "what does the market pay for X", or wants
  to understand hiring trends in their space. Uses the TheirStack MCP to query live job-posting data
  across companies, then turns it into actionable talent intel — hiring signals, tech stacks, where
  to source, and how the company's offer compares.
---

# Competitor Talent Intelligence

## What This Skill Does

Turns **competitors' job postings into talent strategy.** Companies broadcast their priorities,
growth, and gaps through what they hire for. This skill uses the **TheirStack MCP** (live access to
200M+ job postings across hundreds of thousands of sources) to read those signals and turn them into
decisions: where to source, who's vulnerable to poaching, what the market pays, and where the company
is competing for the same people.

---

## Prerequisites

This skill depends on the **TheirStack MCP**. If it isn't connected, say so and point the user to
enable it — don't fabricate hiring data. TheirStack's free tier covers light use; heavier analysis
may need a paid plan.

> **Note:** TheirStack's coverage is strongest for companies that actively post jobs. A competitor in
> a hiring freeze, or a very small team that rarely posts, will show thin — flag this rather than
> reading silence as a signal.

---

## Process

1. **Clarify the question.** Sourcing ("where do I find X people"), competitive ("what's [company]
   building"), or market ("what does this role pay / require now")?
2. **Query TheirStack** for the relevant postings — by company, role, location, tech stack, or
   recency.
3. **Read the signals:**
   - **Growth/priority signals:** what a competitor is hiring for reveals where they're investing.
   - **Poaching angles:** roles being backfilled, teams scaling, possible churn.
   - **Market benchmark:** what comparable roles require and pay right now.
   - **Sourcing pools:** which companies are training up the exact people you want.
4. **Translate to action** — don't just report data, say what to *do* with it.

---

## How to Produce Useful Intel

- **End with a decision, not a dashboard.** "Acme is scaling their growth team — likely churn in 3–6
  months, worth building relationships now" beats a table of postings.
- **Read patterns, not single posts.** One job listing is noise; a cluster of related roles is a
  signal about strategy.
- **Flag coverage gaps honestly.** Thin data on a quiet competitor isn't "they're not hiring" — it's
  "we can't see it." Say so.
- **Tie market data back to the user's open roles** — "you're competing with these 4 companies for
  this profile, and they're paying X" is directly actionable.

---

## Output Format

```
# Talent Intel: [Question / Company / Market]
**Source:** TheirStack · **Caveat:** [coverage note if relevant]

## What the data shows
[Patterns, not a raw dump. Clusters of hiring, trends, comp/skill benchmarks.]

## Signals
- **Growth/priority:** ...
- **Poaching angles:** ...
- **Market benchmark:** ...
- **Sourcing pools:** ...

## What I'd do with this
[Concrete actions tied to the user's hiring needs — who to target, when, how the offer should look.]
```

---

## Intel Failure Checklist

This FAILS if it:
- ❌ Dumps raw posting data without translating to action
- ❌ Reads a single posting as a strategic signal (needs patterns)
- ❌ Treats thin coverage of a quiet competitor as "not hiring"
- ❌ Fabricates numbers when TheirStack isn't connected or returns nothing
- ❌ Reports market comp without tying it to the user's actual open roles
