# agentRankTool

A visual aid for Ideal Execution interviewers. Share your screen, show the client the automation candidates, and drag them into the order the client gives you. The top three are highlighted. Cross out the ones that are not worth pursuing, then copy the result into your notes.

It is one file, `index.html`. No install, no build, no server, no network calls.

## Use it

1. Open `index.html` in Chrome, Edge, Safari or Firefox. The first time, it shows a sample list.
2. Click **Edit list**, paste your candidates (one per line), and click **Save list**.
3. Share your screen and rank with the client:
   - Drag any row to move it. The top three are highlighted.
   - Click the X to rule a candidate out. It moves to a crossed-out "Ruled out" list. The arrow icon brings it back.
   - Double-click a name or summary to reword it.
4. Click **Copy results** to copy the ranking as plain text for notes or email.

### Input format

One candidate per line: the name, then a separator, then a one-sentence summary.

```
Invoice Matching Agent - Matches incoming invoices to purchase orders and flags mismatches.
Customer Inquiry Triage: Reads inbound emails, tags the intent and routes them.
Weekly KPI Report Builder — Pulls numbers from source systems and drafts the report.
```

- Separators: ` - ` (with spaces), `:`, `|`, an en or em dash, or a tab. Two columns pasted from Excel or Sheets work as is.
- Bullets, numbering, `**bold**` and Markdown table pipes are stripped.
- A name with no summary is fine.
- **Edit list** shows the current order. Saving keeps a candidate's ruled-out state if its name is unchanged. To start the next client, replace the whole text with the new list.

### Keyboard

Click a row (or Tab to it) first.

| Key | Action |
| --- | --- |
| Alt + Up / Down | Move the row up or down one rank |
| Up / Down | Move focus to the previous or next row |
| X | Rule out or bring back |
| Enter | Rename |
| Esc | Cancel a drag or an edit |

## Distribute it

Pick one:

- **Send the file.** Share `index.html` over Slack, Teams or email. Interviewers save it and double-click it. Works offline.
- **GitHub Pages.** In the repo, go to Settings, then Pages, then deploy from the `main` branch, root folder. Everyone gets the same URL and updates roll out on merge. Pages on a private repo needs a paid GitHub plan, and the site itself is public unless your org has Enterprise Cloud private Pages. That is acceptable here because the file contains no client data (see below).
- **Any static web host** (SharePoint document library links usually download HTML instead of opening it, so test first).

## Data and privacy

- Everything the interviewer types stays in that browser's local storage. Nothing is sent anywhere.
- The ranking survives a page refresh. Each browser holds one list at a time.
- Before starting the next client, copy the results, then replace the list with **Edit list**.
- On a shared or client-owned computer, replace or clear the list at the end of the session.

## Change it

All the code, styles and logic are in `index.html`. Colors and font follow the playbook visual spec in `intake-agent-1` (`plugin/playbook-docx/skills/playbook-docx/renderer/style.py`), set on a dark background. They are CSS variables at the top of the file.
