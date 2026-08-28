# Prior History (pre-purchase)

> **⚠️ FABRICATED.** No such vehicle or history exists.

Source: vehicle history report pulled 2026-04-28 at 117,350 mi, days before
purchase. In a real record the PDF and its `.txt` extraction sit in this folder;
such reports are licensed and may not be redistributed, which is one reason a
real instance of this repository stays private.

**9 service records · 2 previous owners.**

## Title and damage

| Check | Result |
|---|---|
| Accidents / damage | None reported |
| Structural damage | None reported |
| Airbag deployment | None reported |
| Title brands | Reported clean |
| Odometer rollback | No indication |

## Ownership timeline

| | Owner 1 | Owner 2 | Owner 3 (you) |
|---|---|---|---|
| Purchased | 2016 | 2021 | 2026-05-02 |
| Held for | 5 yr 2 mo | 4 yr 10 mo | — |
| Use | Personal | Personal | Personal |
| Miles/yr | ~14,600 | ~8,700 | ~5,000 |
| Ending odometer | 75,400 | 117,350 | — |

## Service history as reported

| Date | Miles | Where | Work |
|---|---|---|---|
| 2016-09-14 | 7,120 | Selling dealer | Oil and filter, tire rotation |
| 2017-06-02 | 18,940 | Selling dealer | Oil and filter, multi-point inspection |
| 2018-04-19 | 33,600 | Selling dealer | Oil and filter, cabin filter, tire rotation |
| 2019-08-08 | 52,110 | Independent shop | Oil and filter, front brake pads and rotors |
| 2020-11-30 | 68,220 | Independent shop | Oil and filter, transfer case fluid |
| 2021-07-15 | 76,050 | Chevrolet dealer | Oil and filter, **recall 19V645000 performed** |
| 2023-03-22 | 94,800 | Independent shop | Oil and filter, four tires fitted |
| 2024-10-05 | 108,400 | Independent shop | Oil and filter, rear brake pads |
| 2026-02-11 | 115,900 | Independent shop | Oil and filter, battery tested |

---

## What this history tells us

### One recall is already done — and that changes the scan reading

**Recall `19V645000` (vacuum power brake assist) was performed 2021-07-15 at
76,050 mi.** That is the recall the `C0299` brake code would otherwise have
pointed straight at.

> **This is exactly why a model-level recall lookup is not enough.** NHTSA's API
> lists `19V645000` as applying to this vehicle, and it does — but it was
> already remedied five years ago. Only a VIN-level lookup, or a service record
> like this one, can tell you that.
>
> `C0299` therefore needs diagnosing on its merits rather than being written off
> as "the recall will fix it." See
> [scans/2026-06-18/analysis.md](../scans/2026-06-18/analysis.md), which was
> written before this record was filed and **has been annotated rather than
> rewritten.**

### Tires date from 2023, and the record agrees with the sidewall

Four tires fitted 2023-03-22 at 94,800 mi. The DOT codes read at the 2026-05-20
inspection are `2521` — week 25 of 2021, roughly 21 months before fitment.

**That is normal**, not evidence of anything wrong: tires commonly sit in
distribution for a year or more. Recorded because the discrepancy looks alarming
if you meet it cold in five years without this note.

At 118,050 mi the tires have covered roughly **23,000 miles**.

### No transmission service on record — and a `[verify]` lead

No transmission fluid service appears in nine records across 118,000 miles.

**Absence of a record is not evidence of absence of service** — two of these
owners used independent shops, and not everything gets reported. But it is
supporting evidence, and it sits alongside `P0700`/`P0711` in the June scan.

### A quiet stretch, and what it does not mean

Between 2024-10-05 (108,400 mi) and 2026-02-11 (115,900 mi) there is a ~7,500
mile gap with one oil change and nothing else reported.

Treat wear items in that window as **unverified**, not as neglected.
