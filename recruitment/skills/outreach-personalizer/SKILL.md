---
name: outreach-personalizer
description: >
  Write personalized candidate outreach messages that get replies — not templates. Use this skill
  whenever the user wants to "reach out to a candidate", "write a sourcing message", "draft outreach",
  "message this person on LinkedIn/email", or is running a sourcing campaign. Connects to Apollo via
  MCP to enrich candidate context (role, company, background) so the message references something
  real about the person. Produces outreach that sounds human and specific, never mass-blast.
---

# Candidate Outreach Personalizer

## What This Skill Does

Writes **personalized cold outreach to candidates** — the kind that gets opened and answered because
it references something real about the person, not "I came across your profile." Optionally uses the
**Apollo MCP** to enrich the candidate (current role, company, background, contact data) so the
message has a genuine hook.

The bar: a message the candidate couldn't tell was sent to 200 other people.

---

## Process

1. **Get the candidate + role.** A name, LinkedIn URL, or profile dump, plus the role you're sourcing
   for and why they'd be a fit.
2. **Enrich via Apollo MCP** (optional): pull current role, company, tenure, background to find a
   specific, true hook. If Apollo isn't connected, say so and work from what's provided.
3. **Find the real hook.** Something specific to *them* — a project, a company they're at, a path they
   took. Generic flattery ("impressive background") is not a hook.
4. **Write short.** Cold outreach lives or dies on brevity. Lead with the hook, say why them
   specifically, make one clear ask, leave an easy out.
5. **Offer variants** — e.g., a warm/curious version and a direct version — so the user picks the
   register.

> **Action boundary:** This skill *drafts* outreach. It does not send. Sending on the user's behalf
> requires their explicit go-ahead each time — present the draft and let them send it.

---

## How to Write Outreach That Works

- **Specific hook first.** "Saw you took Vooma's onboarding from manual to self-serve" beats "your
  background is impressive."
- **Say why *them*, not why the job.** Candidates get pitched roles constantly. Being told why *they
  specifically* came to mind is rarer and lands.
- **One ask.** A 15-minute call, or "open to hearing about it?" — not a wall of role detail.
- **Sound like a person.** Contractions, short sentences, no corporate throat-clearing. Match the
  user's own voice if known.
- **Easy out.** "No worries if the timing's off" lowers the cost of replying, which paradoxically
  raises reply rates.
- **Never fabricate the hook.** If enrichment turns up nothing specific, say so — a weak honest
  message beats a fake-specific one that gets caught.

---

## Output Format

```
# Outreach: [Candidate] → [Role]
**Hook used:** [the specific, true detail]

**Variant A — [register, e.g. "Warm / curious"]**
[subject line if email]
[message]

**Variant B — [register, e.g. "Direct"]**
[subject line if email]
[message]

*Note: drafts only — review and send yourself.*
```

---

## Outreach Failure Checklist

A message FAILS if it:
- ❌ Could have been sent to anyone (no real, specific hook)
- ❌ Leads with the job instead of why this person specifically
- ❌ Runs long — cold outreach must be short
- ❌ Sounds corporate or AI-generated (symmetry, throat-clearing, buzzwords)
- ❌ Makes multiple asks or no clear ask
- ❌ Fabricates a detail about the candidate to manufacture specificity
- ❌ Gets sent automatically instead of handed to the user to send
