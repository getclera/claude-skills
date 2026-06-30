# Job-Seeker Skills — Setup & Usage Guide

10 Claude skills built for job-seekers. The focus is **finding the right roles and winning them** —
research, prep, positioning, negotiation, and decisions. Deliberately *not* about auto-applying or
spamming applications; every skill is about giving you an information and preparation edge a human
can't easily assemble alone.

This guide covers: (1) what each skill does, (2) how to install them, (3) the two MCPs that three
skills use and how to connect them, and (4) when to reach for each.

---

## Quick Start (5 minutes)

1. **Turn on the prerequisite.** Claude.ai → **Settings → Capabilities → "Code execution and file
   creation"** (ON). Skills don't work without it.
2. **Install each `.skill` file** (steps below). They arrive **off** — toggle each on.
3. **Connect the 2 MCPs** only if you want the connected features. 7 of 10 skills need no setup.
4. **Feed each skill as much context as you can.** Every one of these is built to get better the more
   you give it — the JD, the resume, the transcript, the real details. Thin input = thin output.

---

## The 10 Skills

### Before the interview

**1. interview-prep-dossier** — *The flagship.* Scrapes the company website (via Firecrawl) + reads
the pasted JD + your uploaded resume → a full prep dossier: what the company really does, what they'll
probe, how to connect your background to the role, and smart questions to ask. *(Needs Firecrawl MCP.)*
> *Try: "I have an interview at [company] — here's the JD and my resume, the site is [url]. Prep me."*

**2. interviewer-dossier** — Upload your interviewer's LinkedIn profile (exported as PDF) → the
"sauce": their career arc, what they know cold, what they likely value in a hire, and rapport hooks.
> *Try: "Here's my interviewer's LinkedIn PDF — what should I know about them?"*

**3. interviewer-research** — Searches the web for your interviewer's talks, podcasts, articles, and
posts → what they actually think and care about, so you can engage them genuinely. Pairs with #2.
> *Try: "Look up what [name] at [company] has said publicly before my interview."*

**4. strengths-and-gaps** — Reads the JD + your background, then probes with *specific* questions to
find what you genuinely match (and should highlight hard) vs. where you're thin (and how to build an
honest story). Built on the premise: you got the interview, so you can do the job — this is about
positioning.
> *Try: "Here's the JD and my resume — help me figure out what to emphasize."*

**5. story-bank-builder** — Interviews you *casually* (not interrogation-style) to pull out 8–10 strong
STAR stories, mapped to the competencies your target role tests. Walk in with a loaded bank.
> *Try: "I freeze on behavioral questions — help me build my stories for a PM role."*

### Positioning & strategy

**6. career-pivot-translator** — For career-changers. Translates your real experience into the target
field's language — honest resume bullets + a pivot narrative + what you'll genuinely need to build.
> *Try: "I'm a teacher trying to move into product management — help me translate my experience."*

**7. startup-career-finder** — Startup-exclusive. Asks sharp questions about what energizes you and
what you've done, then points you to *real* startup roles that fit — holding an elite bar, and honest
when full-time startup life isn't your fit (e.g. suggesting fractional instead).
> *Try: "I want to work at a startup but don't know what role fits me."*

### Money & decisions

**8. comp-negotiation** — Pulls live market data for your role/level/location, tells you where an offer
sits, and writes the actual negotiation scripts — including the awkward "what are your expectations?"
moment and the graceful walk.
> *Try: "They offered $X for a [role] in [city] — help me figure out what to counter."*

**9. offer-decision-tool** — Weighs offers (or offer vs. staying) across comp, equity, growth, manager,
risk, and life fit — framed around *your* priorities, with honest equity modeling and a clear call.
> *Try: "I have two offers — help me decide."*

**10. application-post-mortem** — You got rejected or ghosted. Reviews the role, your materials, and
what happened (interview transcripts via a note-taker MCP or pasted) → an honest read on why, and what
to change. *(Optional note-taker MCP.)*
> *Try: "I made it to the final round and got rejected — help me figure out what went wrong."*

---

## How to Install a Skill (per file)

Do this once for each of the 10 `.skill` files:

1. Make sure **Code execution and file creation** is ON (Settings → Capabilities).
2. In Claude.ai's left sidebar, click **Customize** (or profile → Settings → Skills).
3. Click **Skills**.
4. Click the **+** button → **Create skill** → **Upload a skill**.
5. Select the `.skill` file → **Open**.
6. The skill appears **off** — **toggle it on.**

Once on, Claude loads each automatically when your request matches — no need to name the skill.
Uploaded skills are private to your account.

---

## How to Connect the MCPs

Three skills use external connectors. You connect via **Customize → Connectors** in Claude.ai, then
authenticate. The other 7 skills need nothing.

### Firecrawl (for interview-prep-dossier) — needed for the company scrape

Firecrawl is added as a **custom connector** with your API key in the URL:

1. Sign up at **firecrawl.dev** and copy your API key (free tier: 500 credits, plenty for prep use).
2. In Claude.ai go to **Customize → Connectors → "+" → Add custom connector**.
3. Name it `Firecrawl` and set the URL to:
   **`https://mcp.firecrawl.dev/YOUR_API_KEY/v2/mcp`** (replace `YOUR_API_KEY` with your real key).
   - Prefer not to put the key in the URL? Use the keyless endpoint **`https://mcp.firecrawl.dev/v2/mcp`**
     instead, and Claude will open a browser sign-in to authorize.
4. Leave the OAuth fields blank. Click **Add**.
5. Enable Firecrawl per-conversation via the **"+"** button in the chat composer.

If you can't connect it, the dossier skill falls back to working from the JD + resume and any pages
you paste — just with weaker company intel.

### Note-taker MCP (optional, for application-post-mortem) — only if pulling interview transcripts

If you recorded your interviews with a note-taker, you can connect it so Claude reads the transcript
directly. **Granola, Fathom, Otter, and Fireflies all have Claude MCP connectors.**

1. **Customize → Connectors.** Look for your note-taker in the directory; if it's there, click
   **Connect**. If not, add it as a custom connector with its MCP URL (check the tool's docs).
2. Authenticate via OAuth.
3. Enable it in the chat via the **"+"** button.

You never *have* to connect this — pasting the transcript or your notes works just as well. The skill
will ask which note-taker you use and check for an MCP; if there's none or you'd rather not, it takes
a paste.

> **Note on transcript access:** some note-takers gate full transcripts behind paid tiers (e.g.
> Granola transcripts need a Business plan). If the connector returns thin data, paste instead.

### Web search (for interviewer-research) — built in

No setup. The interviewer-research skill uses Claude's built-in web search. Just make sure web search
is enabled in your settings.

> **General connector notes:** Custom connectors connect from Anthropic's cloud, so the server must be
> publicly reachable. Free Claude accounts can add only **one** custom connector; Pro/Max/Team/
> Enterprise support more. Connectors are enabled **per conversation** via the "+" menu.

---

## When to Use Each (a typical search)

These don't run in a fixed order — pull the one that matches your moment:

- **Exploring direction** → startup-career-finder
- **Changing fields** → career-pivot-translator
- **Got an interview** → interview-prep-dossier, then strengths-and-gaps, then story-bank-builder
- **Know who's interviewing you** → interviewer-dossier + interviewer-research
- **Got an offer** → comp-negotiation, then offer-decision-tool
- **Got rejected** → application-post-mortem (then loop back stronger)

---

## Two Things Every Skill Is Built Around

1. **Feed it maximum context.** Each skill pushes you for the JD, the resume, the transcript, the real
   details — because output quality is capped by input quality. Don't give it "help me prep" and stop;
   give it everything.
2. **The bar is elite and the advice is honest.** These won't tell you you're a perfect fit for
   everything, won't inflate your experience into lies, and won't pretend a full-time startup job
   suits someone who wants to coast. Honest beats flattering when your career's on the line.

---

## Troubleshooting

| Problem | Fix |
|---|---|
| Skill won't trigger | Confirm it's toggled **on** in Customize → Skills, and Code execution is enabled. |
| "Code execution required" | Settings → Capabilities → enable Code execution and file creation. |
| Firecrawl not scraping | Check the connector is enabled in the current chat ("+" menu) and your API key is in the URL. |
| Out of Firecrawl credits | Free tier is 500 credits/month; each scrape uses some. Upgrade or space out usage. |
| Note-taker returns no transcript | Likely a paid-tier gate — just paste the transcript instead. |
| Interviewer-research finds wrong person | Give the skill the interviewer's company + role to disambiguate same-named people. |
| Want to edit a skill | Re-upload an updated `.skill` file. |
