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
| **Overall condition** | Unknown — nothing inspected or filed yet |
| **Documents on file** | None |

**This record was created today and is empty.** That is the honest status, and
saying so is better than an optimistic summary of nothing.

## Open action items

1. **Gather the paperwork.** Whatever came with the truck — bill of sale, any
   service receipts, the window sticker if it survived.
2. **Get a vehicle history report** and file the digest.
3. **Get a pre-purchase or baseline inspection**, and ask for *measurements*
   rather than adjectives. "Brakes good" is worthless in three years; a pad
   thickness is a wear rate.
4. **Photograph and transcribe the data plates** — door jamb and glovebox —
   before there is any chance of the truck being sold with them.

## How this record works

```
.
├── _inbox/            ← drop new documents here, any name, they get filed
├── README.md          ← you are here: status, open items, upcoming work
├── CLAUDE.md          what is specific to THIS truck; imports the method
├── .claude/method.md  the shared method, verbatim and versioned (v1.1.0)
└── bin/               check-links · extract-text · inbox-status
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
