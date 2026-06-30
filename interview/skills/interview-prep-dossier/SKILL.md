---
name: interview-prep-dossier
description: >
  Build a complete, personalized interview prep dossier for a specific role. Use this skill whenever
  someone has an interview coming up and says "help me prep for an interview", "I have an interview
  at [company]", "prepare me for this interview", "what should I know before my interview", or pastes
  a job description and wants to get ready. Scrapes the company website via Firecrawl, reads the
  pasted JD, and reads the candidate's uploaded resume, then produces tailored prep: what the company
  does, what they'll likely probe, how to connect the candidate's experience to the role, and smart
  questions to ask. Always gather the company URL, the JD, and the resume before prepping.
---

# Interview Prep Dossier

## What This Skill Does

Builds a **deep, personalized prep dossier** for a specific interview by combining three inputs: the
**company website** (scraped live via Firecrawl), the **job description** (pasted), and the
**candidate's resume** (uploaded). The output prepares the candidate to walk in genuinely informed —
not with generic "research the company" advice, but with specific, role-tailored prep that connects
*their* background to *this* role.

The bar is elite: the dossier should make the candidate sound like the most prepared person the
interviewer talks to all week.

---

## Gather Maximum Context First

Quality of prep is capped by quality of input. Before prepping, collect all three — and push for more
if anything's thin:

1. **Company website URL** (required) — to scrape via Firecrawl. Ask for the careers page, about
   page, blog, and product pages if the homepage is thin.
2. **The job description** (required) — ask the candidate to paste the full JD, not a summary.
3. **The candidate's resume** (required) — ask them to upload it.
4. **Bonus context that sharpens everything** — ask for: who they're interviewing with (name/title),
   the interview round and format, anything the recruiter told them about what to expect, and what
   the candidate is most nervous about. The more they give, the better the dossier.

If the candidate skips something, ask once more — explain that prep quality depends on it. Don't prep
on thin input and call it done.

---

## Process

1. **Scrape the company** via Firecrawl. Pull: what they do, their product, recent news/blog posts,
   their stated values/mission, customers, funding/stage if visible, and how they talk about
   themselves (tone, positioning). Scrape multiple pages if the homepage is thin — map the site, then
   scrape the careers, about, blog, and product pages.
2. **Parse the JD** for: the real responsibilities, the must-haves, the implied "what they're
   actually worried about hiring for," and the language they use (mirror it).
3. **Read the resume** against the JD: where the candidate is strong, where there are gaps, and which
   experiences to lead with.
4. **Synthesize the dossier** (format below).
5. **Pressure-test it.** Generate the hard questions the interviewer is likely to ask given the JD +
   company, and coach the candidate's answers using their actual resume.

---

## Output Format

ALWAYS produce this structure:

```
# Interview Prep: [Role] at [Company]

## The Company (what you need to know cold)
[5–8 tight bullets from the scrape: what they do, stage, recent news, how they position themselves,
who their customers are. Specific, not generic. Recent news is gold — mention it in the interview.]

## What This Role Is Really About
[Read past the JD bullets to the actual job. What problem are they hiring this person to solve? What
will make-or-break success in the role? What are they secretly worried about?]

## Your Fit: Lead With These
[From the resume — the 3–4 strongest connections between the candidate's experience and this role.
Specific bullets they should work into answers.]

## Your Gaps: Get Ahead of These
[Honest read on where the resume is thin vs. the JD, and how to address each — a reframe, a
transferable example, or a "here's how I'd ramp" answer. Never tell them to hide a gap; coach them to
handle it.]

## Questions They'll Likely Ask
[6–10 questions tailored to THIS role + company, each with a one-line "here's how to approach it"
grounded in the candidate's background.]

## Smart Questions to Ask Them
[5–6 questions that signal genuine homework — referencing the company's actual product, news, or
strategy. These make the candidate memorable.]

## Night-Before Checklist
[Logistics + the 3 things to absolutely nail.]
```

---

## Prerequisite: Firecrawl MCP

This skill scrapes the company site via **Firecrawl MCP**. If it isn't connected, say so and give the
setup (custom connector, URL `https://mcp.firecrawl.dev/YOUR_API_KEY/v2/mcp`, or the keyless endpoint
`https://mcp.firecrawl.dev/v2/mcp`). If the candidate can't connect it, fall back: ask them to paste
key pages, or work from the JD + resume alone — but flag that the company intel will be weaker.

---

## Quality Bar / Failure Checklist

This dossier FAILS if it:
- ❌ Gives generic "research the company, dress well" advice instead of role-specific prep
- ❌ Doesn't tie the candidate's actual resume to the actual role
- ❌ Tells the candidate to hide gaps instead of coaching how to handle them
- ❌ Suggests questions-to-ask that could be asked at any company (no evidence of real homework)
- ❌ Ignores recent company news/blog content that would make the candidate stand out
- ❌ Preps on thin input without first pushing for the JD, resume, and company URL
