# Recruitment Skills — Setup & Usage Guide

A set of 10 Claude skills built for a Head of Recruitment. They cover the full hiring loop: writing
JDs, screening CVs, scoring interviews, building rubrics, candidate outreach, offers, rejections,
intake briefs, and competitor talent intelligence.

This guide covers: (1) what each skill does, (2) how to install them, (3) how to connect the MCPs
that three of them depend on, and (4) the order to use them in.

---

## Quick Start (5 minutes)

1. **Turn on the prerequisite setting.** In Claude.ai: **Settings → Capabilities → toggle on "Code
   execution and file creation."** Skills don't work without this.
2. **Install each `.skill` file** (steps below). They arrive switched **off** — turn each one on.
3. **Connect the 3 MCPs** if you want the connected features (steps below). The other 7 skills work
   with no setup.
4. **Build a rubric first** for any role — the screening and scoring skills lean on it.

---

## The 10 Skills

### Core (no setup needed — work immediately)

**1. rubric-builder** — *Start here.* Builds a weighted, behaviorally-anchored interview scorecard
for a role. Encodes 5 dimensions: quality of questions asked, evidence of slope (learning rate),
self-awareness, culture fit, and real work output (weighted heaviest). This is the spine — the
screener and call-scorer score against it.
> *Try: "Build a rubric for a Growth Strategist role, small team, customer-facing."*

**2. jd-writer** — Writes full job descriptions using a proven structure (proof of momentum → vision
→ team → product → role → honest must-haves). Optionally benchmarks against the market via TheirStack.
> *Try: "Write a JD for a senior backend engineer, Series A, remote."*

**3. cv-screener** — Takes a batch of CVs + a role and returns a ranked shortlist with reasons and
red flags. First-pass filter; surfaces close calls for you to review.
> *Try: upload CVs + a JD → "Screen these and rank who to interview."*

**4. interview-questions** — Generates a structured question bank (behavioral, competency,
situational), each with what a strong vs. weak answer sounds like, tied to rubric dimensions.
> *Try: "Interview questions for a mid-level PM, assessing judgment and slope."*

**5. offer-letter** — Turns the basics (candidate, comp, start date, reporting line) into a clean,
warm, professional offer letter. Flags anything that needs legal/HR review. Drafts only — doesn't send.
> *Try: "Draft an offer for Jane Doe, Senior Designer, $145k base, starts March 3."*

**6. rejection-writer** — Writes warm, specific rejections that protect your employer brand. Tone
scales with how far the candidate got. Drafts only.
> *Try: "Write a rejection for a final-round candidate we're passing on."*

**7. hiring-brief** — Creates the intake document before a search starts: ideal-candidate profile,
anti-patterns, sourcing strategy, interview plan, timeline. Aligns you and the hiring manager.
> *Try: "Build a hiring brief for our first sales hire."*

### Connected (need an MCP — see setup below)

**8. call-scorer** — Pulls candidate interview calls from **Granola** and scores each candidate
against the rubric, with evidence from the transcript. *(Needs Granola MCP.)*
> *Try: "Pull this week's candidate interviews from Granola and score them."*

**9. outreach-personalizer** — Writes personalized candidate outreach, enriching context via
**Apollo**. Drafts only — doesn't send. *(Apollo MCP optional but recommended.)*
> *Try: "Write outreach to this candidate for our growth role."*

**10. competitor-talent-intel** — Analyzes competitors' hiring via **TheirStack** job-posting data:
where to source, who to poach, market comp. *(Needs TheirStack MCP.)*
> *Try: "Who is [competitor] hiring right now and what does it tell us?"*

---

## How to Install a Skill (per file)

Do this once for each of the 10 `.skill` files.

1. Make sure **Code execution and file creation** is ON (Settings → Capabilities).
2. In the left sidebar of Claude.ai, click **Customize** (or profile icon → Settings → Skills).
3. Click **Skills**.
4. Click the **+** button → **Create skill** → **Upload a skill**.
5. Select the `.skill` file → **Open**.
6. The skill appears in your list, switched **off**. **Toggle it on.**

Repeat for all 10. Once on, Claude loads each automatically when your request matches it — no need to
name the skill.

**Team/Enterprise note:** if you're on a Team or Enterprise plan, an Owner must first enable **Code
execution and file creation** AND **Skills** under *Organization settings → Skills*. Owners can also
upload these org-wide so the whole recruiting team gets them in one shot (*Organization settings →
Skills → Upload*). Personal uploads stay private to your account unless shared.

---

## How to Connect the MCPs

Three skills use external connectors. Here's how to wire each one up. In all cases you connect via
**Customize → Connectors → "+" button** in Claude.ai, then authenticate with OAuth (Claude never
sees your password).

### Granola (for call-scorer)

Granola has a **native connector** — easiest path:

1. Go to **Customize → Connectors** in Claude.ai.
2. Look for **Granola** in the connectors directory and click **Connect**.
3. Authenticate via the browser OAuth flow — **sign in with the same email your Granola account
   uses** (check it in Granola: Settings → your profile email, top left).
4. Enable Granola per-conversation via the **"+"** button in the chat composer.

**Two limits that matter for scoring:**
- **Transcripts require a Granola Business plan or higher.** On Basic/free, the connector only sees
  the last 30 days of notes and *no transcripts.* For real scoring, you want transcripts.
- **The connector only sees the authorizing user's private "My notes" — not shared Team-space
  folders.** If interviews live in a shared workspace, each interviewer connects their own Granola,
  or switch the active workspace in the Granola desktop app (top-left workspace name) so the
  connector points at the right one.
- **Troubleshooting:** if Claude says "no tools available" or finds no notes, reconnect Granola in
  Claude's connector settings (do this on claude.ai even if you use the desktop app), and confirm
  you're on the right account/workspace by asking Claude "which Granola account am I signed in with?"

### Apollo (for outreach-personalizer)

Apollo is already connected on this account. If you ever need to re-add it:

1. **Customize → Connectors → "+"** → find **Apollo** in the directory → **Connect**.
2. Authenticate with your Apollo login via OAuth.
3. Enable it per-conversation via the **"+"** button.

Apollo enriches candidate context (role, company, background). The outreach skill works without it —
it just has less to personalize on. It **drafts** outreach; it never sends.

### TheirStack (for jd-writer benchmarking + competitor-talent-intel)

TheirStack is a **custom connector** (not in the default directory), so you add it by URL:

1. Go to **Customize → Connectors**.
2. Click the **"+"** button → **Add custom connector**.
3. Enter a name (e.g. `TheirStack`) and the MCP server URL: **`https://mcp.theirstack.com`**
   *(confirm the exact URL on TheirStack's MCP docs — they use OAuth, so no API key juggling).*
4. Click **Add**, then complete the OAuth sign-in.
5. Enable it per-conversation via the **"+"** button.

**Plan note:** TheirStack's free tier includes MCP access with ~200 credits/month — fine for light
use. Heavy competitor analysis may need a paid plan ($59/mo tier). Coverage is strongest for
companies that actively post jobs; a competitor in a hiring freeze will show thin data.

> **General connector notes:** Custom connectors connect from Anthropic's cloud, not your laptop, so
> the server must be reachable on the public internet. Free Claude accounts can add only **one**
> custom connector; Pro/Max/Team/Enterprise support more. Connectors are enabled **per conversation**
> via the "+" menu — if a connected skill isn't pulling data, check the connector is toggled on in
> that chat.

---

## Recommended Workflow Order

The skills are designed to chain. A typical role runs like this:

1. **hiring-brief** — align with the hiring manager on who you're looking for.
2. **rubric-builder** — build the scorecard for the role. *(Do this before screening/scoring.)*
3. **jd-writer** — write the posting (benchmark via TheirStack if connected).
4. **outreach-personalizer** — source and reach out (Apollo-enriched).
5. **cv-screener** — rank inbound + sourced CVs into a shortlist.
6. **interview-questions** — prep the panel with a structured guide.
7. **call-scorer** — score the interviews from Granola against the rubric.
8. **offer-letter** — extend to the hire.
9. **rejection-writer** — close the loop warmly with everyone else.
10. **competitor-talent-intel** — ongoing, between searches, to inform strategy.

---

## Two Things to Know

- **The rubric is the backbone.** call-scorer, cv-screener, and interview-questions all sharpen when
  there's an explicit rubric to work against. Build it first per role rather than letting the skills
  invent criteria on the fly.
- **The action skills draft, they don't send.** offer-letter, rejection-writer, and
  outreach-personalizer produce drafts for you to review and send yourself. This is deliberate —
  auto-sending candidate communications is how employer brands get burned.

---

## Troubleshooting

| Problem | Fix |
|---|---|
| Skill won't trigger | Confirm it's toggled **on** in Customize → Skills, and Code execution is enabled. |
| "Code execution required" | Settings → Capabilities → enable Code execution and file creation. |
| Granola returns nothing | Wrong workspace/account, or Team-space notes (connector only sees private notes). Reconnect on claude.ai. |
| No transcript in scoring | Granola transcripts need a Business plan; Basic gives notes only. |
| TheirStack/Apollo not pulling | Enable the connector in the current chat via the "+" menu. |
| Want to edit a skill | Re-upload an updated `.skill` file (or remove and re-add a custom connector). |
