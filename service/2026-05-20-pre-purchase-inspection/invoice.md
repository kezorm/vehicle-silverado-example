# Pre-Purchase Inspection — Invoice Transcription

> **⚠️ FABRICATED.** No such inspection took place. This demonstrates how an
> invoice is transcribed and what gets kept.

**Shop:** Cedar Street Automotive, 118 Cedar St, Ashfield
**Invoice:** 44821 · **Date:** 2026-05-20 · **Odometer:** 117,890 mi
**Requested by:** buyer, pre-purchase · **Technician:** M. Alvarez (ASE A1–A8)

Original PDF: `invoice-44821.pdf` (with `invoice-44821.txt` beside it, per the
extraction convention).

---

## Every line item, as billed

| # | Description | Qty | Parts | Labor | Total |
|---|---|---|---|---|---|
| 1 | Pre-purchase inspection, 120-point | 1 | — | 1.5 hr @ $140 | $210.00 |
| 2 | Engine oil and filter change — 0W-20 dexos1 Gen 2 | 6 qt | $42.00 | 0.5 hr | $112.00 |
| 3 | Oil filter, ACDelco PF63 | 1 | $9.50 | — | $9.50 |
| 4 | Cabin air filter — replaced, prior filter heavily loaded | 1 | $24.00 | 0.2 hr | $52.00 |
| 5 | Engine air filter — inspected, within service limits, **not replaced** | 1 | — | — | $0.00 |
| 6 | Brake measurement, all four corners | 1 | — | 0.3 hr | $42.00 |
| 7 | Tire tread depth measurement, all five | 1 | — | — | $0.00 |
| 8 | Battery load test | 1 | — | — | $0.00 |
| 9 | Shop supplies | — | $11.75 | — | $11.75 |
| | | | | **Total** | **$437.25** |

**Why line 5 is here.** It cost nothing and prompted no action. It is recorded
because in 2029 the question "when was the engine air filter last changed?" has
a different answer if we know it was *inspected and passed* at 117,890 than if
we have no record at all. **A line item that changed nothing is still a fact
about a date.**

---

## Measurements taken — the reason this invoice matters most

Numbers, not adjectives. "Brakes good" is worthless in three years; a set of
measurements is a baseline you can subtract from.

### Brake friction material

| Corner | Pad remaining | Rotor thickness | Discard spec |
|---|---|---|---|
| Left front | 7.0 mm | 27.4 mm | 26.0 mm |
| Right front | 7.5 mm | 27.5 mm | 26.0 mm |
| Left rear | 8.0 mm | 19.3 mm | 18.0 mm |
| Right rear | 8.0 mm | 19.4 mm | 18.0 mm |

### Tire tread depth (32nds)

| | Outer | Centre | Inner | DOT |
|---|---|---|---|---|
| LF | 7 | 7 | 6 | 2521 |
| RF | 7 | 7 | 6 | 2521 |
| LR | 8 | 8 | 8 | 2521 |
| RR | 8 | 8 | 8 | 2521 |
| Spare | 10 | 10 | 10 | 1116 |

**Two findings fall straight out of the table**, and neither was written on the
invoice — this is what a digest is for:

1. **The fronts wear on the inner edge**, one to two 32nds down from the outer.
   Consistent across both sides, which points at alignment rather than a single
   worn component. Worth an alignment check, cheap, and it protects tires that
   still have most of their life.
2. **The spare is from 2016 and original to the truck** (DOT `1116` = week 11 of
   2016; the road tires are `2521`, week 25 of 2021). It has full tread and is
   ten years old. Tread is not the constraint on a spare — age is.

### Battery

| Test | Result |
|---|---|
| Rated | 730 CCA |
| Measured | 611 CCA |
| State of health | 84% |
| Verdict | Passed; retest at next service |

---

## Technician notes, transcribed verbatim

> "Slight tick from top end on cold start, goes away when warm. No misfire
> felt on test drive. Customer advised to monitor. Oil looks clean, no metal
> on the plug."

**Recorded verbatim and left un-interpreted.** In May this read as an
unremarkable note. After the June scan it reads very differently — a cold-start
tick on an AFM engine is the first symptom owners report before lifter failure.
See [`../../scans/2026-06-18/analysis.md`](../../scans/2026-06-18/analysis.md).

> **This is the entire argument for capturing completely.** Nobody at the time
> knew which sentence on this invoice would matter. Had the filing pass kept
> only "what changed" — the oil and the cabin filter — the single most
> diagnostically useful sentence in the document would have been thrown away
> four weeks before it became the key to a $4,000 question.
