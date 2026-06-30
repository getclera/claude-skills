---
name: interview-questions
description: >
  Generate a structured interview question bank for a specific role, seniority, and the traits being
  hired for. Use this skill whenever the user says "give me interview questions", "what should I ask
  this candidate", "build an interview guide", "questions for a [role] interview", or is preparing a
  hiring panel. Produces competency, behavioral, and role-specific questions, each with what a good
  vs. bad answer looks like, so interviewers know what they're listening for.
---

# Interview Question Generator

## What This Skill Does

Produces a **structured interview question bank** tailored to a role, seniority level, and the
specific traits being assessed. Crucially, each question comes with **what a strong answer vs. a weak
answer looks like** — so the interviewer isn't just asking questions, they know what signal to listen
for. This keeps a panel aligned and stops interviews from becoming unstructured chats.

---

## Process

1. **Get the inputs:** role, seniority, and the 3–5 traits/competencies being hired for (pull from
   the rubric if one exists). Ask if missing.
2. **Generate questions in three buckets:**
   - **Behavioral** — past behavior as predictor ("Tell me about a time...")
   - **Competency / technical** — can they actually do the work
   - **Role-specific / situational** — judgment in scenarios they'll actually face
3. **For each question, write the listen-for:** what a 5-answer sounds like, what a 1-answer sounds
   like. This is the part that makes the guide useful.
4. **Tie questions to rubric dimensions** where one exists, so scoring is clean.
5. **Include probes** — follow-ups that dig past a rehearsed first answer.

---

## How to Write Good Questions

- **Behavioral beats hypothetical.** "Tell me about a time you shipped something nobody asked for"
  surfaces real slope. "What would you do if..." invites a rehearsed ideal answer.
- **Make questions surface the rubric signals:** quality of thinking (ask open questions and watch
  what they ask back), slope, self-awareness (poke holes in their answers and watch them adapt).
- **Tie at least one question to self-awareness under pushback** — present something they did and
  challenge it; the adaptation is the signal.
- **Avoid trivia and gotchas.** They test memory and nerves, not the job.
- **Calibrate to seniority.** A senior hire should face ambiguity and tradeoff questions; a junior
  hire, fundamentals and learning speed.

---

## Output Format

```
# Interview Guide: [Role] — [Seniority]
**Assessing:** [the traits/competencies]

## Behavioral
**Q:** [question]
→ *Strong answer:* [what good sounds like]
→ *Weak answer:* [what a red flag sounds like]
→ *Probe:* [follow-up]
*(Maps to: [rubric dimension])*

## Competency / Technical
[same structure]

## Role-Specific / Situational
[same structure]

## Open Floor (Quality-of-Questions test)
[Reminder to leave space for the candidate's questions and treat what they ask as data.]
```

---

## Question Failure Checklist

A guide FAILS if it:
- ❌ Asks questions with no "listen-for" — leaving interviewers to guess what's good
- ❌ Leans on hypotheticals where behavioral questions would surface real evidence
- ❌ Uses trivia/gotchas that test nerves, not the job
- ❌ Isn't calibrated to seniority
- ❌ Doesn't surface the rubric's key signals (slope, self-awareness, quality of thinking)
- ❌ Has no probes, so a rehearsed first answer ends the thread
