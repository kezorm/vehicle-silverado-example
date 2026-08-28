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
| **Last known odometer** | 117,400 mi *(2026-05-02, at purchase)* |
| **Overall condition** | Unknown — nothing inspected yet |
| **Build** | 5.3L V8 (`L83`) · 8L90 8-speed · 4WD · 3.42 locking rear axle ([vehicle.md](vehicle.md)) |
| **Warranty** | All factory coverage expired. Recalls and special coverage are unaffected. |
| **Documents on file** | Window sticker transcription |

Paid $18,400 against an original MSRP of $45,920 — a **60% decline over ten
years and 117,400 miles**.

## Open action items

1. **Get a pre-purchase or baseline inspection**, and ask for *measurements*
   rather than adjectives. "Brakes good" is worthless in three years; a pad
   thickness is a wear rate.
2. **Photograph and transcribe the data plates** — door jamb and glovebox.
3. **Get a vehicle history report** and file the digest.
4. **Chase the original window sticker PDF.** GM makes these retrievable by VIN
   for many model years. Worth doing before the information is needed, not after.

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
└── purchase/          window sticker + digests
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
