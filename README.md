# 2016 Chevrolet Silverado 1500 LT 4WD — Vehicle Record

> ## ⚠️ This is a public example. The vehicle does not exist.
>
> It demonstrates a method for keeping an object's history as a version-
> controlled record that an AI assistant maintains alongside you.
>
> **Fabricated:** the truck, its VIN, every date, every odometer reading, the
> purchase, the service history, the invoice, the data plates, and the
> diagnostic scan.
>
> **Real:** every diagnostic trouble code definition, all NHTSA recall and
> complaint data (cited by campaign and ODI number, retrieved 2026-08-27), and
> the documented failure modes of the GM 5.3L L83 and 8L90.
>
> **Never use a figure here to decide anything about a real vehicle.** What is
> worth copying is the method — see [`CLAUDE.md`](CLAUDE.md) and
> [Adapting this](#adapting-this-for-your-own-object) at the bottom.

**Owned since** 2026-05-02 · **Full specs:** [vehicle.md](vehicle.md)

---

## Current status

| | |
|---|---|
| **Last known odometer** | 118,050 mi *(2026-06-18)* |
| **Miles since purchase** | 650 |
| **Overall condition** | Drives normally. **Check engine light on**, steady. |
| **Emissions** | **NOT READY** — EVAP monitor incomplete; would fail an OBD inspection today |
| **Airbags / SRS** | No codes |
| **Last diagnostic scan** | [2026-06-18](scans/2026-06-18/analysis.md) — 23 codes, 9 assessed as one network event |
| **Factory warranty** | All expired. Recalls and special coverage are unaffected. |
| **History** | 2 prior owners, no accidents, no title brands ([details](purchase/prior-history.md)) |
| **Last work done** | 2026-05-20 at 117,890 mi — pre-purchase inspection, oil, cabin filter |
| **Tires** | LT265/70R17, fitted 2023 at 94,800 mi, ~23,000 mi on them. Spare is **original to the truck, 10 years old** |

---

## Open action items

Ranked. Nothing here is an emergency, but item 1 is the one that decides whether
this truck is worth keeping.

### 1. Confirm or rule out AFM lifter failure

**Six engine codes, and the pattern is the diagnosis.** Misfires on cylinders
**1, 4, 6 and 7** — exactly the four that Active Fuel Management deactivates —
with 2, 3, 5 and 8 clean. Four coils do not fail at once, and would not choose
the AFM set if they did.

Supporting evidence arrived *before* the codes did: the pre-purchase inspection
recorded a **cold-start tick that disappeared when warm**, which is the symptom
owners report first.

**This is the expensive one.** Confirm with cylinder compression or a borescope
before authorising work.

- [ ] Compression test or borescope, cylinders 1/4/6/7
- [ ] Oil level and condition checked (AFM lifters are oil-pressure operated)

Reasoning: [reference/known-issues.md](reference/known-issues.md)

### 2. Have a dealer run the VIN — free, do first

Two separate things a scan tool cannot tell you:

- **`19V761000`** (ABS wheel speed sensor / tone ring) shows no record of being
  performed. Recall work is free.
- **Special coverage** may cover the transmission harness behind `P0700`/`P0711`.
  Manufacturer-funded programs are not in NHTSA's database and no scan tool
  reports them. **`[verify]`** — sourced from an owner complaint, not a GM
  document.

Ask: *"are there any open recalls, campaigns, or special coverage programs
against this VIN?"*

- [ ] VIN run at nhtsa.gov/recalls
- [ ] Dealer asked about campaigns **and** special coverage

Details: [reference/recalls-and-tsbs.md](reference/recalls-and-tsbs.md)

### 3. Diagnose `C0299` on its merits — the recall will not cover it

Brake booster large vacuum leak, **Confirmed**, no warning light, normal pedal.

The obvious move would be to attribute this to open recall `19V645000` and let
the dealer fix it free. **That is wrong here:** the service history shows that
recall was already performed in 2021 at 76,050 mi, and the code set anyway.

**Watch for:** a pedal harder than usual on a cold start.

- [ ] `C0299` diagnosed

### 4. Front alignment — cheap, protects tires with life left

Both front tires wear one to two 32nds low on the **inner** edge, consistent
across both sides. That pattern points at alignment, not a worn component.

Tires are at 6–7/32" with ~23,000 miles on them. Correcting alignment now
protects the remaining life; leaving it wastes it.

- [ ] Four-wheel alignment · measured before/after readings filed

### 5. Steering — do not buy hardware yet

`C056D`, power steering control module internal failure, **Confirmed**. GM's own
guidance says not to replace the module on a history-only code, and bulletin
**PI1273** addresses this presentation by **reprogramming**. `[verify]` — PI1273
is written against the 2014 truck.

- [ ] Re-scan before authorising any steering work

### 6. Clear codes and re-scan — the decisive step

After items 1 and 2: clear all codes, drive 1–2 weeks with several cold starts,
re-scan. Whatever returns **Confirmed** is real; the rest was history. This turns
23 codes into a short work order.

- [ ] Codes cleared — date: \_\_\_\_\_\_
- [ ] Re-scan performed — date: \_\_\_\_\_\_

### Worth doing at the next service

- [ ] **Transmission drain-and-fill.** No fluid service on record in 118,000
      miles. Uses low-viscosity ATF — **not** generic Dexron VI, which is a known
      cause of shudder on this unit.
- [ ] **Replace the spare tire.** Full tread, but original to the truck and ten
      years old. On a spare, age is the constraint.
- [ ] **Retest the battery.** 611 CCA against 730 rated, 84% health, May 2026.
      A second reading makes it a trend rather than an opinion.

### Done

- [x] **Oil and filter** — 2026-05-20 at 117,890 mi, 0W-20 dexos1 Gen 2
- [x] **Cabin air filter** — 2026-05-20, prior filter heavily loaded
- [x] **Baseline measurements** — brakes, tires, battery all measured and filed

---

## Upcoming maintenance

**Which limit binds: the calendar, not the odometer.** At ~5,000 miles a year,
every mileage interval on this truck arrives long after its calendar equivalent.

| Item | Interval | Binding limit |
|---|---|---|
| Engine oil | Oil Life Monitor | **Annual.** The monitor is a usage algorithm; oil ages in the sump regardless and the monitor will never prompt you. |
| Brake fluid | By condition / date | **Calendar.** Absorbs moisture whether driven or not. |
| Tires | Tread depth | **Age**, for the spare. Tread is irrelevant at ten years. |

---

## How this repository is organized

```
.
├── _inbox/            ← drop new documents here, any name, they get filed
├── README.md          ← you are here: status, open items, upcoming work
├── CLAUDE.md          what is specific to THIS truck; imports the method
├── .claude/method.md  the shared method, verbatim and versioned (v1.1.0)
├── vehicle.md         identity, ownership, warranty status
├── bin/               check-links · extract-text · inbox-status
├── purchase/          window sticker, prior history + digests
├── service/           work performed since purchase, with invoices
├── scans/             diagnostic scans, one dated folder each
│   ├── code-baseline.md    all 23 codes, triaged — the comparison baseline
│   └── 2026-06-18/         codes.json, analysis
└── reference/         fluids, parts, recalls, known issues
    └── labels/        transcriptions of the data plates
```

## The archival half — what this record is really for

The ranked list above is the **episodic** job: it will be empty one day. The
documents below are the **cumulative** job, and they are why the record is worth
keeping after every item above is closed.

| Document | Actionable today? | Why it is here |
|---|---|---|
| [reference/labels/](reference/labels/README.md) | **No** | RPO codes, GAWR, paint, axle ratio. The answer to "which rear axle?" in 2034, when the label is long gone with the truck. |
| [purchase/window-sticker.md](purchase/window-sticker.md) | **No** | The only complete statement of how it left the factory. Settles which equipment is original and which a previous owner added. |
| [service/…/invoice.md](service/2026-05-20-pre-purchase-inspection/invoice.md) | **Partly** | Full line items and measurements — including a line that changed nothing and a technician's offhand remark that turned out to be the key to item 1. |
| [purchase/prior-history.md](purchase/prior-history.md) | **Partly** | Which recall was already performed. Without it, item 3 would have been mis-triaged as free dealer work. |

**Each of those was captured by asking "what does this document say?" rather
than "what does this change?"** The second question would have discarded all of
it, and two of the four turned out to matter within weeks.

## Adding documents

Drop anything into [`_inbox/`](_inbox/) — receipts, invoices, scan reports,
photos of paperwork. No naming convention needed. Then say **"check the inbox."**

```sh
./bin/inbox-status     # what is waiting
./bin/extract-text     # write .txt beside every PDF, flag tabular ones
./bin/check-links      # verify every relative link before committing
```

---

## Adapting this for your own object

Nothing here is vehicle-specific except the contents. The method transfers to
anything with a service life, a document trail, and questions that arrive years
later — a boat, a house, an instrument, a machine.

1. **Copy the skeleton, not the content.** Keep `.claude/method.md` *verbatim*,
   `bin/`, and `_inbox/README.md`; write your own `CLAUDE.md` for the specifics.
   Empty everything else — and resist pre-creating folders. Make one when a
   document arrives that needs it.
2. **Capture completely; triage separately.** The filing pass is the only moment
   anyone has the document open and is paying attention.
3. **Baseline early.** One scan is uninterpretable; the second is a work order.
   The same is true of any measurement.
4. **Record numbers, not adjectives.** "Brakes good" is worthless in three
   years; 7.0 mm is a wear rate.
5. **Never write that something "was skipped"** because no record of it exists.
   Write "no record of X since \<date\>."
6. **Flag your own weakest claim** in every research pass.
7. **Keep a real record private.** It accumulates purchase prices, licensed
   reports, and identifiers. Going public is one-way.

**The one rule that makes it work** is in the imported method
([`.claude/method.md`](.claude/method.md)): new information gets propagated to
every document it affects — the artifact, the digest, *and* this status page —
in the same sitting. A record whose front page has drifted out of date is worse
than none, because it is confidently wrong.

The two-file split is deliberate. `.claude/method.md` is byte-identical in every
record built this way, so updating it later is "replace one file, review the
other for conflicts" rather than reconciling prose. `CLAUDE.md` imports it with
`@.claude/method.md` — an import expanded into context at launch, not a link
read at the model's discretion. Everything specific to this truck goes in
`CLAUDE.md`; the method file is never edited.

*Every figure in this example is fabricated. The method is not.*

---

### A note on this repository's history

`git log` here is a **narrated reconstruction**, not a forensic trace. The
commits were authored in one sitting and are dated accordingly — they are not
backdated to the fabricated 2026-05-02 → 2026-06-18 timeline in the content.

What the sequence *is* faithful to is the shape of the work: setup first,
folders created only when a document needed one, the status page updated in
every commit, and a conclusion inverted in the last one by a document that
arrived late. Reading `git log --reverse` is the fastest way to see the method
run start to finish.
