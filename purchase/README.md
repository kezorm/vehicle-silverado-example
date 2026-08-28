# Purchase

> **⚠️ FABRICATED.** No such purchase occurred.

**Purchased 2026-05-02 at 117,400 miles**, private sale, as third owner.

| | |
|---|---|
| Purchase price | $18,400 |
| Original MSRP (2016) | $45,920 |
| Decline | 60% over 10 years and 117,400 miles |

## Documents on file

| What | Where |
|---|---|
| Vehicle history report | *not included — licensed, may not be redistributed* |
| Window sticker transcription | [window-sticker.md](window-sticker.md) |
| Prior history digest | [prior-history.md](prior-history.md) |

Each PDF in a real record is kept byte-intact with a `.txt` extraction beside
it, so the content stays searchable without a PDF reader. Run `bin/extract-text`.

## Still missing

A record tracks its own gaps rather than pretending to be complete:

- [ ] Bill of sale
- [ ] Title
- [ ] Registration
- [ ] Original window sticker PDF — **retrievable from GM by VIN**, worth doing
      before the information is needed rather than after

## Note on sensitive documents

Purchase paperwork is the most likely place for account numbers and signatures
to enter a repository like this, and **git history is permanent** — deleting a
file later does not remove it from past commits.

A bill of sale, title, or financing paperwork gets an explicit decision — track
it, gitignore it in place, or keep only a redacted summary — **before** the first
commit that would contain it. See [`../_inbox/README.md`](../_inbox/README.md).
