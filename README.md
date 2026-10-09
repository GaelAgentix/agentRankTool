# agentRankTool

A visual aid for Ideal Execution interviewers. Share your screen, show the client the automation candidates, and drag them into the order the client gives you. Star the ones they love, cross out the non-starters, and copy the result into your notes.

It is one file, `index.html`. No install, no build, no server, no network calls.

## Use it

1. Open `index.html` in Chrome, Edge, Safari or Firefox.
2. Paste the candidates into the text box, one per line, and click **Build ranking**.
3. Type the client or session name in the title.
4. Click **Present** to hide the controls before you share your screen. Press **Esc** to get them back.
5. Rank with the client:
   - Drag any row to move it. Rank numbers update as you drag.
   - Click the star to mark a favorite.
   - Click the X to rule a candidate out. It moves to a greyed, crossed-out "Ruled out" list. The arrow icon brings it back.
   - Double-click a name or summary to reword it.
   - Type in the "+ Add a candidate" box to add one that comes up during the call.
6. When you are done, click **Copy results** (plain text for notes or email) or **CSV** (for a spreadsheet).

The top 3 rows are highlighted in navy. A dashed "Top 4" cut line sits under rank 4. Change either number with **Highlight top** and **Cut line after**.

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
- **Edit list** reopens the text box with the current order. Lines you keep hold on to their star and ruled-out state; new lines are added where you put them.

### Keyboard shortcuts

Click a row (or Tab to it) first.

| Key | Action |
| --- | --- |
| Alt + Up / Down | Move the row up or down one rank |
| Up / Down | Move focus to the previous or next row |
| S | Star or unstar |
| X | Rule out or bring back |
| Delete | Delete a ruled-out row |
| Enter | Rename |
| Ctrl/Cmd + Z | Undo |
| Esc | Cancel a drag, cancel an edit, or leave Present mode |

## Distribute it

Pick one:

- **Send the file.** Share `index.html` over Slack, Teams or email. Interviewers save it and double-click it. Works offline.
- **GitHub Pages.** In the repo, go to Settings, then Pages, then deploy from the `main` branch, root folder. Everyone gets the same URL and updates roll out on merge. Pages on a private repo needs a paid GitHub plan, and the site itself is public unless your org has Enterprise Cloud private Pages. That is acceptable here because the file contains no client data (see below).
- **Any static web host** (SharePoint document library links usually download HTML instead of opening it, so test first).

## Data and privacy

- Everything the interviewer types stays in that browser's local storage. Nothing is sent anywhere.
- The ranking survives a page refresh. Each browser holds one session at a time.
- Before starting the next client, copy or download the results, then open **Edit list** and click **Clear everything**.
- On a shared or client-owned computer, always clear at the end of the session.

## Change it

All the code, styles and logic are in `index.html`. Colors and font follow the playbook visual spec in `intake-agent-1` (`plugin/playbook-docx/skills/playbook-docx/renderer/style.py`): navy `#1F3864`, accent `#2E5496`, pale `#D9E2F3`, band `#F2F5FB`, red `#C00000`, Arial. They are CSS variables at the top of the file.
