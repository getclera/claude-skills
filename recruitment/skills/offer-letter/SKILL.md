---
name: offer-letter
description: >
  Generate clean, professional offer letters from a few inputs. Use this skill whenever the user
  wants to "write an offer letter", "draft an offer", "make an offer for [candidate]", or is
  extending a role to a hire. Produces a complete, warm-but-professional offer letter and can flag if
  comp falls outside a defined band. Note: this drafts the letter — it does not send it or commit the
  company to terms.
---

# Offer Letter Generator

## What This Skill Does

Turns the basics — candidate, role, comp, start date, reporting line — into a **clean, complete,
professional offer letter** that's warm enough to close and clear enough to avoid confusion. Saves
the 20 minutes of formatting and second-guessing per hire.

---

## Process

1. **Collect the essentials:** candidate name, role title, employment type, base comp, equity (if
   any), start date, reporting line, location/work type, and any conditions (e.g., contingent on
   references / background check).
2. **Optional band check:** if the user has defined a salary range for the role, flag whether the
   offer is below / within / above band before drafting.
3. **Draft the letter** — professional, warm, unambiguous. Cover the role, comp, start, reporting,
   conditions, and a clear next step (sign-by date).
4. **Flag what needs legal/HR review** — at-will language, benefits specifics, equity terms vary by
   company and jurisdiction. Note these rather than inventing them.

> **Boundaries:** This skill drafts. It does not send the offer, and it is not legal advice. Comp
> figures, equity terms, and legal clauses must be confirmed by the user / their counsel. Flag
> anything you're filling as a placeholder.

---

## How to Write a Good Offer

- **Warm, not stiff.** The candidate should feel wanted. A line of genuine enthusiasm before the
  terms helps close.
- **Unambiguous on the numbers.** Base, equity, start date, reporting line — no vagueness.
- **Clear next step.** A sign-by date and how to accept. Ambiguity here stalls closes.
- **Flag placeholders.** If you don't have a real number, mark it `[CONFIRM: base salary]` — never
  invent comp.
- **Note jurisdiction-dependent clauses** for review rather than asserting them.

---

## Output Format

```
# Offer Letter: [Candidate] — [Role]
[Band check, if applicable: "Offer is [within/above/below] the defined band of [range]."]

---
[Date]

Dear [Name],

[Warm opening — genuine enthusiasm about them joining.]

[Role, reporting line, location/work type.]

**The offer:**
- Base: [amount]
- Equity: [amount / details]  [or CONFIRM placeholder]
- Start date: [date]
- [Other terms]

[Conditions, if any — references, background check.]

[Clear next step + sign-by date.]

[Warm close, signature block.]
---

⚠️ Review before sending: [list jurisdiction-dependent / legal items to confirm — at-will language,
benefits, equity terms.]
```

---

## Offer Failure Checklist

An offer FAILS if it:
- ❌ Invents comp, equity, or terms instead of flagging placeholders
- ❌ Is stiff/transactional enough to cool a candidate who's deciding between offers
- ❌ Leaves the numbers or start date ambiguous
- ❌ Has no clear acceptance step or sign-by date
- ❌ Asserts legal clauses as final instead of flagging them for review
- ❌ Gets sent automatically instead of handed to the user
