# agentRankTool

A visual aid for Ideal Execution interviewers. Share your screen, show the client the automation candidates, and drag them into the order the client gives you. The top three are highlighted in orange. Cross out the ones that are not worth pursuing, then copy the result into your notes.

It is one file, `index.html`. No install, no build, no server, no network calls.

## Use it

1. Open `index.html` in Chrome, Edge, Safari or Firefox. It opens on an empty list.
2. Paste your candidates (one per line) and click **Save list**. **Edit list** reopens the text box later.
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

- Everything the interviewer types stays in that browser tab (session storage). Nothing is sent anywhere.
- The ranking survives a page refresh. Closing the tab clears it, and a new tab or window always opens empty, so one client's list never shows up in front of the next client.
- Copy the results before closing the tab.

## Use it from a presentation

Put a link on the candidates slide that opens the tool in the browser (for example a button labelled "Open ranking tool"). Links survive export to PDF from PowerPoint, Keynote and Google Slides, and stay clickable in Acrobat, Preview and browser PDF viewers. Point the link at a hosted copy (GitHub Pages or a shared link), not at a file path, which breaks on other people's computers. Share your whole screen, or switch the shared window, when you jump from the deck to the tool. After the call, paste **Copy results** into the readout deck.

Embedding the HTML file inside a PDF is not worth it: most PDF viewers cannot open attachments, and none run the page inside the PDF.

## Change it

All the code, styles and logic are in `index.html`. It follows the Agentix Live FDE house style (`ashahid-agentix/fde-house-style`), using the dark deck palette from `tokens/deck.css` (navy `#0E1B33` background, orange `#E86A1F` accent) and Geist / Geist Mono. The colors are CSS variables at the top of the file. The Geist fonts (SIL Open Font License) are embedded as data URIs, copied from the house style's `fonts/` folder, so the page works offline.
