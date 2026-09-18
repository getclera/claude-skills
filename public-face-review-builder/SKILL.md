---
name: public-face-review-builder
description: Turn a supplied people/contact list with names, profile-picture URLs, roles, LinkedIn URLs, and optional owner fields into a mobile-friendly face-memorization web app with grid, quiz, flashcard, shuffle, and filtering modes, then publish it to a shareable public URL when an approved writable hosting destination is available. Use when the user wants to memorize attendees, founders, candidates, customers, investors, or other people before an event or meeting.
---

# Public Face Review Builder

Create a lightweight visual study app from a user-supplied people list and, when possible, publish it as a public static page.

## Inputs

Accept any structured or semi-structured source that contains some of the following fields:

- name
- LinkedIn/profile URL
- profile-picture URL
- owner / assigned person
- company
- role / title
- notes

The source may be Markdown, CSV, spreadsheet, document, pasted text, or another attached file.

Treat the supplied source as authoritative. Preserve its terminology and do not invent missing facts.

## Step 1 — Read and normalize the source

1. Read the complete attached/source file, not just a truncated preview.
2. Extract one record per person.
3. Normalize to this internal shape:

```text
{
  name,
  linkedin,
  pic,
  owner,
  role
}
```

4. Deduplicate obvious exact duplicates by name + profile URL.
5. Preserve blank values when information is missing.
6. Never infer a missing headshot, company, role, or LinkedIn URL.
7. Count:
   - total people
   - people with profile-picture URLs
   - people missing profile-picture URLs

If the source contains an owner/assignee field, preserve it for filtering.

## Step 2 — Build the static review app

Create a self-contained static site using plain HTML, CSS, and JavaScript. Prefer no build step and no framework unless the user explicitly asks for one.

The app must include these modes:

### Grid

- responsive face grid
- large square images using `object-fit: cover`
- visible name
- visible company / role
- optional owner label
- neutral placeholder for missing/broken images

### Grid Quiz

- same grid layout
- hide identity details initially
- clicking/tapping a card reveals name + role
- each card reveals independently

### Flashcards

- one face at a time
- identity hidden initially
- Reveal button
- Previous and Next controls
- keyboard shortcuts:
  - Space = reveal/hide answer
  - Left Arrow = previous
  - Right Arrow = next

### Shuffle

- randomize the current study order
- reset the flashcard position to the beginning of the shuffled order

### Filters

When a categorical field such as `owner` exists:

- include `Everyone`
- include each distinct owner value found in the source
- filtering must work in grid, quiz, and flashcard modes

Do not hard-code owner names unless they are present in the source.

## Step 3 — Design defaults

Use these defaults unless the user specifies otherwise:

- dark mode
- minimal visual chrome
- no branding
- sticky compact controls
- desktop and mobile responsive
- two columns on narrow mobile screens
- clear focus on faces rather than metadata
- no analytics, cookies, login, or backend

External image URLs may be loaded directly. Use graceful `onerror` fallback to a placeholder.

Do not generate substitute portraits for missing people.

## Step 4 — Package the files

Prefer this structure:

```text
face-review/
  index.html
  app.js
  data.js
```

If the dataset is too large for one file/tool payload, split it into ordered chunks:

```text
face-review/
  index.html
  app.js
  data1.js
  data2.js
  ...
```

`app.js` should concatenate all loaded data arrays into one collection.

Keep the app fully static so it can run from any ordinary static host.

## Step 5 — Validate locally before publishing

Verify at minimum:

1. every parsed person is represented exactly once
2. record count matches the normalized source count
3. grid renders
4. quiz reveal works
5. flashcard reveal works
6. next/previous works
7. shuffle works
8. filters work
9. missing/broken images show placeholders
10. layout remains usable on narrow screens
11. no JavaScript syntax errors
12. no malformed CSS that breaks card layout

If an automated browser is unavailable, validate the generated source structurally and inspect the final HTML/JS files directly.

## Step 6 — Publish publicly

The user wants a URL that another person can open without access to the current chat.

Preferred options, in order:

1. an explicitly designated static-hosting provider or public-site connector
2. a dedicated public GitHub repository owned by the user/organization
3. an existing public repository that the user has explicitly identified as an approved hosting destination

### GitHub static publishing

When using GitHub:

1. confirm the target repository is public
2. confirm the connected integration has write access
3. write the app under an isolated path such as `face-review/`
4. never overwrite unrelated existing files
5. never publish into an unrelated public repository merely because it is writable
6. use GitHub Pages when already configured and directly usable
7. otherwise, if appropriate, use a trusted raw-to-static renderer only as a fallback and pin the URL to a commit SHA so later repository changes do not unexpectedly change the artifact

If no approved writable public host is available, create the complete static bundle for the user and state that public deployment requires a connected/approved host. Do not claim the local/sandbox file is public.

## Step 7 — Verify the live page

Before returning the final answer, verify as much as the available tools allow:

- the files exist at the committed paths
- all required data chunks exist
- `index.html` references the correct files
- the published URL resolves without authentication when live browsing is available
- the URL points to the intended version

If live URL verification is impossible, say that the files were published but live unauthenticated access could not be independently confirmed.

## Step 8 — Privacy and sharing warning

Because the output is public, clearly tell the user that the names, roles, external profile-picture URLs, and any other included metadata are publicly accessible through the page/source.

Do not include private emails, phone numbers, passwords, internal notes, or non-public personal data in a public deployment unless the user explicitly requests that specific information be published and it is appropriate to do so.

## Final response

Keep the response concise. Include:

- the public shareable URL, if successfully published
- the local/downloadable artifact only as an optional backup
- a one-line summary of modes included
- a short privacy note that the page is public

Do not call a sandbox link a public link.

## Reuse behavior

On future invocations, if the user supplies a new attendee/contact list, rerun the workflow from the source rather than reusing stale people data.

If the user asks to update an already-published face review app, modify the existing approved deployment when possible instead of creating a duplicate site.
