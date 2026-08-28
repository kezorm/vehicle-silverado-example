# Working rules — 2016 Chevrolet Silverado 1500 (example record)

The shared method for records like this one is imported below and applies in
full. This file holds only what is specific to **this vehicle and this
repository**.

@.claude/method.md

> `.claude/method.md` is a verbatim copy of the asset-record skill's template,
> currently **v1.1.0**. Don't edit it — record-specific rules go here instead.
> To bring it up to date, replace that file wholesale from the current skill and
> review this one for conflicts.

---

> ## ⚠️ This record is a public example. The vehicle does not exist.
>
> **Fabricated:** the truck, its VIN, every date and odometer reading, the
> purchase, the service history, the invoice, the data plates, and the
> diagnostic scan.
>
> **Real:** every diagnostic trouble code definition, all NHTSA recall and
> complaint data (cited by campaign and ODI number, retrieved 2026-08-27), and
> the documented failure modes of the GM 5.3L L83 and 8L90.
>
> Never use a figure here to decide anything about a real vehicle. What is worth
> copying is the method.

## Orientation

Read this file, then `README.md` — current status and ranked open items.

Nothing is filed yet. The first documents to arrive should be the purchase
paperwork and anything the seller handed over.

## What this record has learned the hard way

*(Nothing yet — this record was created today. Entries go here as they are
learned: a source that proved unreliable, a gap in the paperwork that turned out
to hide real work, a number that was wrong the first time. These are worth more
than the rules they illustrate, because they are why anyone believes them.)*

## Record-specific conventions

- **Never write a well-formed VIN in this record.** Use the literal placeholder
  `<VIN — example, no real vehicle>`. A plausible 17-character string decodes to
  somebody's actual truck.
- **Every file states its fabrication status.** Any new document added here
  carries a marker in its first few lines. A reader arriving at one file deep
  from a search engine must not mistake it for a real vehicle's record.
- **Fabricate the arrangement, never the facts.** Code numbers, code
  definitions, recall campaign numbers, ODI numbers and documented failure modes
  are real and checked. The invention is only that they co-occurred on one
  truck. Keep that line if this example is extended — it is what separates a
  demonstration from a misleading one.
- **Miles are the unit.** Record the odometer with every event.
- **Which limit binds: the calendar.** At ~5,000 mi/year every mileage interval
  here arrives long after its calendar equivalent. The standing examples are
  annual oil changes (the Oil Life Monitor is a usage algorithm and will never
  prompt you) and the spare tire, which has full tread at ten years old.

## Filing routing

| What arrives | Where it goes |
|---|---|
| | |

*(Empty on purpose. Fill a row in when a document arrives and a folder is made
for it — see the method on why an empty guessed-at tree is worse than none.)*

## Repository facts

| | |
|---|---|
| Remote | *(none — not published)* |
| Branch | `main` |
| Visibility | Intended to be **public**; safe because nothing here is real |

This is the inverse of a normal record. The method's *Before sharing* section
assumes a private record holding an owner's real information; this one exists to
be read. The audit still applies to anything added: check that no real VIN, real
person, or third-party copyrighted document enters it.

## Environment notes that are not obvious

- Poppler is installed on this machine (`pdftotext`, `pdfseparate`, `pdftoppm`);
  `qpdf` and `gs` are not. `docling` is installed user-level via
  `uv tool install docling`.
- No PDFs are filed yet, so `bin/extract-text` reports nothing. Expected.

## Committing

Commit messages state the finding, not the file move:

```
<what was learned, in one line>

<why it matters, what changed as a result>
```
