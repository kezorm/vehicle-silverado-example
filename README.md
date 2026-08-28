# 2016 Chevrolet Silverado 1500 LT 4WD — Vehicle Record

> ## ⚠️ This is a public example. The vehicle does not exist.
>
> Everything about the truck is fabricated. Diagnostic code definitions and
> NHTSA data added later are real and cited. Never use a figure here to decide
> anything about a real vehicle.

**Owned since** 2026-05-02 at 117,400 miles.

---

## Current status

| | |
|---|---|
| **Last known odometer** | 118,050 mi *(2026-06-18)* |
| **Overall condition** | Drives normally. **Check engine light on**, steady. |
| **Emissions** | **NOT READY** — EVAP monitor incomplete; would fail an OBD inspection today |
| **Last diagnostic scan** | [2026-06-18](scans/2026-06-18/analysis.md) — 23 codes, 9 assessed as one network event |
| **Build** | 5.3L V8 (`L83`) · 8L90 8-speed · 4WD · 3.42 locking rear axle ([vehicle.md](vehicle.md)) |
| **Warranty** | All factory coverage expired. Recalls and special coverage are unaffected. |
| **Documents on file** | Window sticker · data plates · inspection invoice |
| **Last work done** | 2026-05-20 at 117,890 mi — oil, cabin filter, full measurement baseline |

Paid $18,400 against an original MSRP of $45,920 — a **60% decline over ten
years and 117,400 miles**.

## Open action items

### 1. Confirm or rule out AFM lifter failure

**Six engine codes, and the pattern is the diagnosis.** Misfires on cylinders
**1, 4, 6 and 7** — exactly the four that Active Fuel Management deactivates —
with 2, 3, 5 and 8 clean. Four coils do not fail at once, and would not choose
the AFM set if they did.

**The supporting evidence arrived a month early.** The May inspection recorded a
cold-start tick that disappeared when warm — the symptom owners report first.

- [ ] Compression test or borescope, cylinders 1/4/6/7
- [ ] Oil level and condition checked (AFM lifters are oil-pressure operated)

### 2. Clear codes and re-scan — the decisive step

Nine of the 23 codes are "lost communication with \<module\>" across modules
with nothing to do with each other. Every module cannot independently lose the
bus; the bus went down as a unit. Expect most to vanish.

- [ ] Codes cleared · re-scanned after 1–2 weeks with several cold starts

### 3. Front alignment — cheap, and it protects tires with life left

Both front tires wear one to two 32nds low on the **inner** edge, consistent
across both sides. That pattern points at alignment, not a worn component.

Tires are at 6–7/32". Correcting alignment now protects the remaining life;
leaving it wastes it.

- [ ] Four-wheel alignment · measured before/after readings filed

### 4. Replace the spare

Full tread, and **original to the truck** — DOT `1116`, week 11 of 2016, against
`2521` on the road tires. Ten years old. On a spare, age is the constraint and
tread is irrelevant.

- [ ] Spare replaced

### 5. Get a vehicle history report and file the digest

### 6. Chase the original window sticker PDF

GM makes these retrievable by VIN for many model years. Worth doing before the
information is needed, not after.

### Watch

- **Battery at 84% state of health**, 611 CCA against 730 rated. Passed. A
  second reading at the next service makes it a trend rather than an opinion.
- **A cold-start tick** noted by the technician, gone when warm. Recorded
  verbatim and not interpreted.

### Settled so far, and not actionable today

The **RPO label** is transcribed — the block of three-character option codes in
the glovebox that is the authoritative statement of which configuration this
truck actually is. It means nothing this week and is the only answer to "which
transfer case / which axle / which seat trim" once the truck is gone.

### Settled by the window sticker

The **locking rear differential (`G80`) and 3.42 axle (`GT4`) are factory**, not
a previous owner's swap. A parts counter asking "which rear axle?" now has a
documented answer that does not require crawling under the truck.

## How this record works

```
.
├── _inbox/            ← drop new documents here, any name, they get filed
├── README.md          ← you are here: status, open items, upcoming work
├── CLAUDE.md          what is specific to THIS truck; imports the method
├── .claude/method.md  the shared method, verbatim and versioned (v1.1.0)
├── bin/               check-links · extract-text · inbox-status
├── vehicle.md         identity, ownership, warranty status
├── purchase/          window sticker + digests
├── service/           work performed since purchase, with invoices
├── scans/             diagnostic scans, one dated folder each
└── reference/
    └── labels/        transcriptions of the data plates
```

**No other folders yet, on purpose.** They get made when a document arrives that
needs one. An empty guessed-at tree invites filing things where they don't
belong because a slot exists.

## Adding documents

Drop anything into [`_inbox/`](_inbox/) — receipts, invoices, reports, photos of
paperwork. No naming convention needed. Then say **"check the inbox."**

```sh
./bin/inbox-status     # what is waiting
./bin/extract-text     # write .txt beside every PDF, flag tabular ones
./bin/check-links      # verify every relative link before committing
```
