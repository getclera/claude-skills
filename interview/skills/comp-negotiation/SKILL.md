---
name: comp-negotiation
description: >
  Help a job-seeker understand their market worth and negotiate compensation. Use this skill whenever
  someone says "how much should I ask for", "help me negotiate my offer", "what's the market rate for
  [role]", "they asked my salary expectations", "should I counter this offer", or wants to know where
  an offer sits. Pulls live market data on the role/level/location, tells them where they stand, and
  generates the actual negotiation language for their situation — counters, scripts, and how to handle
  the awkward moments. Gather the role, level, location, and offer details first.
---

# Comp & Negotiation

## What This Skill Does

Two jobs: (1) **calibrate** — figure out what the candidate is actually worth for this role, level,
and location using live market data, and where any offer sits in the band; and (2) **arm** — give them
the specific words to negotiate, from "what are your salary expectations?" through countering an offer
to deciding whether to walk.

The bar is elite and honest: real numbers, not vibes, and scripts that sound like a confident
professional, not a script.

---

## Gather Maximum Context First

Negotiation advice is worthless without the specifics. Collect:

1. **Role, level, and location** (required) — and remote vs. onsite, since it shifts bands.
2. **The offer, if there is one** — base, bonus, equity (amount + details), sign-on, benefits. Get
   everything; equity especially.
3. **The candidate's situation** — current comp, competing offers, how badly they need this role, how
   much they want it, their risk tolerance.
4. **Company stage** — a seed startup, a Series C, and a public company negotiate completely
   differently (cash-constrained vs. equity-heavy vs. banded).
5. **What's happened so far** — has a number been said? By whom first? This determines the play.

If a number hasn't been named yet, the strategy is different (anchor management) than if there's an
offer on the table (countering). Establish which situation you're in.

---

## Process

1. **Pull market data.** Search live sources for the role/level/location band — job postings often
   list ranges now; cross-reference multiple sources. Be honest about the spread and confidence.
2. **Place the offer in the band** — below / at / above market, and by how much.
3. **Read the leverage.** Competing offers, scarcity of the skill, how far along they are, how much
   the company seems to want them. Leverage determines how hard to push.
4. **Build the play** — anchor, target, walk-away. Then write the actual language.
5. **Cover the hard moments** — "what are your expectations" before they've shown a number, the
   counter, the "we can't move on base" response, multiple-offer leverage, and the graceful walk.

> **Boundary:** This is market information and negotiation coaching, not financial advice. For equity,
> explain how to *evaluate* it (ask the right questions — strike price, total shares, last
> valuation, vesting) rather than valuing it definitively. Flag that most early equity is high-risk.

---

## Output Format

```
# Comp & Negotiation: [Role], [Level], [Location]

## Where You Stand
[The market band with sources. Where the offer (if any) sits. Honest confidence level on the data.]

## Your Leverage
[Read on how much push the candidate has, and why. Sets how aggressive to be.]

## The Play
[Anchor / target / walk-away. The strategy in 2–3 lines.]

## Scripts
**If they ask your expectations first:** [exact language]
**Your counter:** [exact language with the number and justification]
**If they say base won't move:** [pivot to equity/sign-on/other levers]
**With a competing offer:** [how to use it without bluffing badly]
**The graceful walk:** [if it's below your floor]

## Equity: Questions to Ask
[What to ask to actually evaluate the equity — not a valuation, the questions that get you one.]

## Don't
[2–3 common negotiation mistakes for this specific situation.]
```

---

## Quality Bar / Failure Checklist

This FAILS if it:
- ❌ Gives a number with no market data behind it, or hides the confidence level
- ❌ Produces generic scripts not tailored to the candidate's leverage and situation
- ❌ Values equity definitively instead of teaching how to evaluate it
- ❌ Ignores non-base levers (equity, sign-on, start date, title) when base is capped
- ❌ Advises bluffing a competing offer that doesn't exist
- ❌ Skips gathering the offer details and situation before advising
