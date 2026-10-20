# Legal Work Portfolio — Deployment Guide

A static GitHub Pages website for Alex Stevinson's **fictional** Horizon Manufacturing v. Summit Components litigation-support exercise. No build tool, paid hosting, or server is required.

## Publish

1. Create a free GitHub account, if needed.
2. Create a **public** repository named `YOUR-GITHUB-USERNAME.github.io` (substitute the actual username).
3. Upload **the contents of this folder** to the repository root, not the parent folder or the ZIP archive.
4. Under repository **Settings → Pages → Build and deployment**, select **Deploy from a branch**, `main`, and `/(root)`, then save.
5. Visit `https://YOUR-GITHUB-USERNAME.github.io` after GitHub Pages finishes deploying.

To preview locally before uploading, run `python3 -m http.server 8000` inside this folder, then visit `http://localhost:8000`. Opening `index.html` directly as a `file://` URL may block the JSON fetches.

## Files

- `index.html`: site content and work-product navigation
- `style.css`: styling
- `script.js`: search, filters, and PDF viewer
- `data/evidence.json`: **uploaded** Evidence Index worksheet and custodian values taken from sheet mislabeled Case Chronology
- `data/chronology.json`: **draft reconstructed** 22-event chronology; not actually uploaded in spreadsheet form
- `data/calendar.json`: **uploaded** litigation-calendar worksheet (27 entries)
- `data/memo.html`: online reading copy generated from the uploaded Word memorandum
- `documents/`: 15 original fictional source PDFs
- `work-products/`: original uploaded Excel spreadsheets and downloadable memorandum in Word/PDF

## Editing work products

The site loads editable JSON from `data/`. Dates should remain in `YYYY-MM-DD` format. Each event's `documents` value is an array of IDs, for example `["DOC-004", "DOC-005"]`.

All PDF document IDs link using entries in `data/evidence.json`, where `file` is the relative path of the PDF.

The memorandum HTML was converted from the supplied DOCX. Updating the DOCX alone will not update the HTML reading view or the existing exported PDF; regenerate those together if editing.

## Important prepublication review

1. **The uploaded chronology workbook does not contain event rows.** Its “Evidence Index” worksheet holds document ID/date/title and the “Case Chronology” worksheet holds document ID/date/title/custodian. Review and approve `data/chronology.json` as a **draft**, or provide a corrected event-based worksheet.
2. **All deadline entries are fictional and need a procedural accuracy review.** The spreadsheet does not include rule citations, triggering dates, or actual court orders. Site labels the calendar illustrative/unverified rather than implying legally established deadlines.
3. **Memo formatting:** The uploaded Word document is titled “Unchecked- Mock Memo -2.docx,” and the content spans approximately 3 pages in the parsed view; proofread and approve before using it publicly.
4. **Custodian fields:** The spreadsheet assigns some provisional custodians and labels individuals `Unidentified`; do not present as authenticated discovery metadata.
5. **Privacy:** GitHub Pages is public. Never upload real client/confidential material.
6. **Document citations:** Confirm DOC-001 through DOC-015 map to the intended facts. The memo contains a mix of single and ranged citations. All cited IDs are in the source PDFs.
7. **No resume uploaded with this batch:** The site intentionally contains no résumé link or unverified personal contact details.

## Automated integrity checks

See `QUALITY_CONTROL_REPORT.md` at the site root for the results of the checks run on the generated files.

## Reviewer-oriented revision (October 2026)
The homepage now introduces the purpose and limitations of the exercise, explains the hypothetical plaintiff-side assignment, provides a searchable 15-document source library ahead of the work products, and ends with an explicit skills interpretation. No source PDFs or underlying work-product tables were altered. The Relativity credential is described as **in progress**, not earned; the Colorado notary statement is based on the author's assertion and should be verified before publication.
