# Diagnostic Scan History

Every scan gets its own dated folder containing the original report, a `.txt`
extraction beside it, a parsed `codes.json`, and a written analysis.

## Scan index

| Date | Odometer | Codes | Analysis | Notes |
|---|---|---|---|---|
| 2026-06-18 | 118,050 | 23 | [analysis.md](2026-06-18/analysis.md) | **Fabricated — see the banner.** Baseline, first scan after purchase. Misfires confined to the four AFM cylinders. Nine network codes attributed to one voltage event. |

## Baseline

[**code-baseline.md**](code-baseline.md) — all 23 codes with triage tags.
Compare future scans against this.

## Adding a new scan

```sh
mkdir -p scans/YYYY-MM-DD
# drop the PDF in, then:
bin/extract-text
```

Then write `analysis.md`, add a row above, and update the status table in the
[top-level README](../README.md).

**Heed the TABLES flag.** Scan reports are dense tables, and `pdftotext`
reconstructs columns from character positions. If `bin/extract-text` flags the
report, verify code-to-status pairings against the PDF before parsing them into
`codes.json` — a code silently attached to the wrong status is the worst
possible error in this folder.
