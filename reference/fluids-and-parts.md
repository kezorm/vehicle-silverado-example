# Fluids and Parts Reference

For a **2016 Chevrolet Silverado 1500 LT 4WD**, 5.3L V8 (L83), 8L90 8-speed.

> **⚠️ FABRICATED VEHICLE.** Values marked `[verify]` are the standard
> specification for this engine family, **not** a checked value for a specific
> truck. In a real record, confirm against the owner's manual, the oil filler
> cap, and a VIN parts lookup before buying anything.

> **Confidence note.** `[confirmed]` means checked against a document held in
> this repository. `[verify]` means plausible but unchecked. Nothing here is
> `[confirmed]` in the way a real record's entries would be, because there is no
> real vehicle behind it.

## Engine oil

| Item | Value | Source |
|---|---|---|
| Specification | **dexos1 Gen 2, SAE 0W-20** | `[verify]` |
| Capacity | **8 qt / 7.6 L** (with filter) | `[verify]` |
| Filter | ACDelco PF63 | `[verify]` — as fitted at the 2026-05-20 service |
| Interval | Oil Life Monitor, not a fixed mileage | `[verify]` |

**Read the oil filler cap.** On GM trucks the cap carries the specification, and
it is the fastest authoritative answer available. **Do not trust a text
extraction of a two-column manual page for this** — that exact mistake produced a
wrong oil-grade conclusion in the record this method came from. See the
extraction warning under *Evidence standards* in
[`.claude/method.md`](../.claude/method.md).

> **Which limit binds:** the Oil Life Monitor is a usage algorithm, but oil also
> ages in the sump. On a truck driven little, the calendar binds and the monitor
> will never prompt you. Change annually regardless of what it reads.

## Transmission

| Item | Value | Source |
|---|---|---|
| Unit | **8L90** 8-speed automatic (RPO `MYC`) | `[verify]` |
| Fluid | Dexron ULV / GM low-viscosity ATF — **not** generic Dexron VI | `[verify]` |
| Method | Drain-and-fill, not a pressure flush | `[verify]` |

**The fluid specification is not interchangeable.** The 8L90 uses a
low-viscosity ATF; filling it with conventional Dexron VI is a known cause of
shudder complaints.

## Brakes — measured baseline

Real measurements beat specifications. From the
[2026-05-20 inspection](../service/2026-05-20-pre-purchase-inspection/invoice.md)
at 117,890 mi:

| Corner | Pad | Rotor | Discard |
|---|---|---|---|
| LF | 7.0 mm | 27.4 mm | 26.0 mm |
| RF | 7.5 mm | 27.5 mm | 26.0 mm |
| LR | 8.0 mm | 19.3 mm | 18.0 mm |
| RR | 8.0 mm | 19.4 mm | 18.0 mm |

## Tires

| Item | Value | Source |
|---|---|---|
| Size | LT265/70R17 | `[confirmed]` — door placard transcription |
| Cold pressure | 50 psi front and rear | `[confirmed]` — door placard |
| Spare | LT265/70R17 at 60 psi | `[confirmed]` — door placard |
| Fitted DOT | `2521` (week 25, 2021) road tires; `1116` spare | `[confirmed]` — inspection |

**The spare is original to the truck and ten years old**, with full tread. On a
spare, age is the constraint, not tread. Full transcription:
[labels/README.md](labels/README.md).

## Battery

| Item | Value | Source |
|---|---|---|
| Rated | 730 CCA | `[confirmed]` — inspection |
| Measured 2026-05-20 | 611 CCA, 84% state of health | `[confirmed]` — inspection |

A measured CCA figure with a date is worth far more than "battery tested OK." It
makes the next test a **trend** rather than a fresh opinion.

## To fill in

- [ ] Read the oil filler cap and confirm the specification
- [ ] Transcribe the complete RPO label, including undecoded codes
- [ ] Confirm rear axle ratio from the RPO label, not from a guess
- [ ] Engine air filter part number
- [ ] Transfer case fluid specification and capacity
