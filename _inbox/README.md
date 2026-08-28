# Inbox — drop documents here

> *Part of a public example repository; the vehicle it belongs to does not
> exist. This file describes process only and contains no vehicle data.*

Put anything vehicle-related in this folder and it gets filed. No naming
convention required. Photos of receipts, PDFs, scan reports, emailed invoices,
screenshots — just drop them in, then say **"check the inbox."**

Run `../bin/inbox-status` to see what is waiting.

## What happens to a dropped file

| What it is | Where it lands | What else gets updated |
|---|---|---|
| Purchase paperwork | `purchase/` | `vehicle.md`, `README.md` |
| Diagnostic scan report | `scans/YYYY-MM-DD/` | New `analysis.md`, diff vs `scans/code-baseline.md`, `README.md` status |
| Service invoice or receipt | `service/YYYY-MM-DD-<what>/` | `service/README.md` log, open-item checkboxes in `README.md` |
| Part numbers, fluid specs, manual pages | `reference/` | `reference/fluids-and-parts.md` |
| Recall or campaign notice | `reference/` | `reference/recalls-and-tsbs.md` |
| Photo of a label or data plate | `reference/labels/` | Transcription in `reference/labels/README.md` |
| Anything unclear | stays here | you'll get asked |

Originals are **preserved** — files are renamed and moved, never rewritten or
compressed. Every PDF gets a `.txt` extraction beside it (`bin/extract-text`).

## Contents of this folder are not in version control

Everything except this README is gitignored on purpose:

1. **Unfiled documents are transient.** Once triaged into `service/` or
   `scans/`, a file gets committed there. Tracking it here too puts two copies
   in history.
2. **Some of it will be sensitive.** Purchase and financing paperwork carries
   signatures and account numbers. Anything committed to git persists in history
   permanently — deleting the file later does *not* remove it from past commits.

This is the reversible default. A file can always be committed on purpose after
review; it cannot easily be un-committed.
