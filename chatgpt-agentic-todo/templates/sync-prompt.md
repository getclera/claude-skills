# ChatGPT Agentic ToDo — scheduled suggestion scan

Canonical private Page: __PAGE_URL__
Personal timezone: __TIMEZONE__

Find NEW, genuinely actionable tasks owned by the user and add up to 10 unique entries under the Page's Suggested section only. This job is **read-only outside the Page**: do not send/reply, edit CRM or tickets, change calendar events, execute the tasks, or publish private context.

Before scanning:
1. Read the complete Page (or all task sections) using connected ChatGPT Space tools. Collect every ID/title in Suggested, Today, This week, Later, Done and Dismissed. Preserve all states and all existing edits.
2. Read messages and events since the last successful scan; first-run lookback up to 7 days, weekends included. Use only available and authorized connectors: Gmail inbox + starred/marked followups; Slack DMs, mentions and *all still-open saved messages*; Granola meeting notes with transcript as needed; upcoming calendar prep. Search recent conversation context if available. Never guess a source.
3. Exclude newsletters, outreach blasts, already answered items, delegated items, vague ideas, obsolete work, and duplicates across any status. Cross-check for existing relevant automations to avoid redundant manual tasks.

For each accepted suggestion, append:
- Stable new ID AT-### (unique by observing the Page), imperative title <80 chars, P0/P1/P2 and recommended Today/This week/Later;
- Source category plus real URL/locator, date and who requested it when available;
- `verified open` if corroborated in recent records, otherwise `needs verification`;
- 1–3 sentence action plan sufficient for a future ChatGPT session, with any approval boundaries;
- Due date only when established from source.

Write ONLY to the private Page, preserving every existing task and section. Read back to confirm. If there's a page conflict, reread and reconcile rather than overwrite. If connectors or Page access fail, report which failed and **never fabricate an update**. Optionally regenerate the read-only dashboard snapshot only when supported; if not, label it as stale instead of implying it is live.

Output: count of suggestions added, with brief category breakdown and link to the private Page. Zero suggestions is valid.
