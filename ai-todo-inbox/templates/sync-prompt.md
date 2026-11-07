# Scheduled sync prompt

Use this as the prompt of a recurring scheduled task (for example weekdays at 7:45am and 4:45pm in your time zone). Replace `__ARTIFACT_URL__` with your todo page's claude.ai URL and `__YOUR_NAME__` with your name.

---

Suggest new todos for __YOUR_NAME__ and put them in their todo list artifact as suggestions. Do not send any messages, emails or replies to anyone, and do not change anything outside the todo list.

Todo list artifact: __ARTIFACT_URL__
Its database collection is "tasks" (use the ArtifactData tool, load it with ToolSearch). Document fields: title (string), bucket ("today" | "week" | "later"), done (bool), created (ms timestamp), and for suggestions: suggested: true, source (short string saying where it came from, e.g. "Meeting: Weekly sync, Nov 5", "Email from Jane Doe", "Slack saved: #sales"), plan (string, see step 4), dismissed (bool, set by the user).

Steps:
1. List every document in "tasks" (page through all of them). Note every existing title, including done, suggested and dismissed ones. Never re-suggest anything that is already there in any state, even if worded differently.
2. Look back over the window since the last run (about the last 16 hours; on Monday morning cover since Friday afternoon). Use whichever of these sources are connected:
   - Email: threads where someone is waiting on a reply or an action from the user (inbound, unanswered by them, not newsletters, not automated, not cold outreach). Also emails they starred or labeled for follow-up.
   - Slack DMs and mentions: messages asking the user for something they haven't answered.
   - Slack saved messages: search with the modifier is:saved. Every saved item that is still open is a strong todo signal; check ALL currently saved items each run, not only recent ones.
   - Meeting notes (e.g. Granola): meetings in the window. Find action items the user committed to or was assigned. Check the transcript when the notes are vague.
   - Calendar: today's remaining and tomorrow's meetings that clearly need prep and have no prep todo yet.
3. Keep only real, concrete actions owned by the user. Skip anything already done, anything owned by someone else, and vague items. Usually 0 to 10 suggestions per run. Zero is fine.
4. For each, write:
   - title: short imperative (start with a verb, include the person or company, under 80 characters).
   - plan: 1 to 3 plain sentences another Claude session can act on without searching from scratch: what exactly to do, who it's for, and how to find the context (email subject and sender, Slack channel and who posted, meeting name and date, calendar event). Say what output is expected (e.g. "draft a reply agreeing to Tuesday", "prep a 1-page brief").
   - bucket: "today" if due today/tomorrow or someone is blocked, "week" if this week, else "later".
5. Add them in one ArtifactData batch with op "set", collection "tasks", doc_id "s" + a short unique id, data {title, plan, bucket, done: false, suggested: true, source, created: <now ms>}. Do not touch existing documents.
6. Finish with a short plain summary: how many suggestions were added, grouped by source. If none, say "No new todo suggestions." If a source could not be reached, say which.
