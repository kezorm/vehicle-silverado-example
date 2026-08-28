# Scan Analysis — June 18, 2026

> # ⚠️ THIS SCAN IS FABRICATED
>
> **No such scan was performed. No such truck exists.** This file demonstrates
> how a diagnostic scan gets triaged in this repository; it is not a record of
> any real vehicle.
>
> **What is real:** every DTC number and its description are real, standard
> codes. Every fault *cluster* is drawn from documented failure modes of the
> 2016 Chevrolet Silverado 1500 5.3L, and each is sourced below to a public
> NHTSA complaint (by ODI number) or an open recall campaign. The diagnostic
> reasoning is the reasoning you would actually apply.
>
> **What is invented:** that these particular codes appeared together on one
> truck, on this date, at this odometer.
>
> Nothing here should be used to diagnose a real vehicle.

**Odometer:** 118,050 mi · **Scan date:** 2026-06-18
**Context:** First scan after purchase (2026-05-02 @ 117,400 mi). Truck drives
normally. Check engine light **on**, steady. No brake or airbag warnings.

**Headline totals:** 23 codes across 8 modules, 5 modules clean.

---

## Verdict

Two genuine mechanical findings, one of which is expensive and one of which may
be **free**. Roughly nine codes are network debris rather than independent
faults. Emissions is **not ready** — that matters if inspection is due.

### Clean systems

- **Airbags / SRS: no codes.** Restraint system reports healthy.
- Tire pressure monitor, instrument cluster, transfer case, telematics: no codes.

---

## Finding 1 — the misfire pattern is the diagnosis

Six engine codes, and the pattern matters far more than the count:

| Code | Description |
|---|---|
| `P050D` | Cold Start Rough Idle |
| `P0300` | Random/Multiple Cylinder Misfire |
| `P0301` | **Cylinder 1** Misfire |
| `P0304` | **Cylinder 4** Misfire |
| `P0306` | **Cylinder 6** Misfire |
| `P0307` | **Cylinder 7** Misfire |

**Cylinders 1, 4, 6 and 7 are exactly the four that Active Fuel Management
deactivates on this engine.** Cylinders 2, 3, 5 and 8 are clean.

That is not a coincidence and it is not four independent coil failures. AFM uses
switching lifters on those four cylinders only, and the documented diagnostic
rule is direct: *if misfires appear on the AFM cylinders and the non-AFM
cylinders are clean, you are looking at a lifter problem.* AFM lifter collapse
accounts for a large share of reported failures on this engine family.

`P0521` (oil pressure sensor performance) and `P0016` (crank/cam correlation)
are both **Not Confirmed**, but both are consistent with the same story — AFM
lifter operation is oil-pressure dependent, and a collapsed lifter changes valve
timing on that cylinder. Watch them; don't chase them separately yet.

**This is the expensive one.** Confirm with a cylinder-by-cylinder compression
or a borescope before authorising work.

*Grounded in:* NHTSA complaints ODI **11480638**, **11342428**, **11290127**,
**11220174** — four separate owners reporting `P050D` on this truck, with dealer
diagnoses ranging from fuel injectors to carbon buildup on cylinder 1 valves.
ODI **11330387** reports the same shudder-and-flashing-CEL presentation.

---

## Finding 2 — the transmission codes may be a free repair

| Code | Description |
|---|---|
| `P0700` | Transmission Control System Malfunction |
| `P0711` | Transmission Fluid Temperature Sensor 'A' Circuit Range/Performance |

`P0700` is not a fault in itself — it is the ECM saying "the TCM has a code."
The real one is `P0711`.

**Before paying anyone:** a complaint on this exact truck and transmission
reports that this code pair was addressed under a **GM special coverage
program** covering a transmission wiring harness replacement. Special coverage
programs are manufacturer-funded repairs that extend beyond warranty. **No scan
tool reports them, and they are not in the NHTSA recall database.** You have to
ask a dealer to run the VIN.

> **`[verify]`** — the program number appears in an owner-submitted complaint,
> not in a document from the manufacturer. Treat it as a lead to raise with a
> dealer, not as an established entitlement. Ask: *"are there any open special
> coverage programs or service bulletins against this VIN?"*

`P2723` is **Not Confirmed** and may simply be debris from the same event.

*Grounded in:* ODI **11648955**, **11623044**, **11502976**.

---

## Finding 3 — brake code, and two recalls that bear on it

`C0299` — **Brake Booster Large Vacuum Leak Detected** — is **Confirmed**, with
no brake warning light and normal pedal feel. The EBCM sets it when the brake
booster vacuum sensor reports too little vacuum to assist braking properly.
Documented symptoms are a hard pedal, longer stopping distances, and a hiss from
the booster area.

Two open recall campaigns for this vehicle are directly relevant:

| Campaign | Component |
|---|---|
| **19V645000** | Service brakes, hydraulic: **power assist: vacuum** |
| **19V761000** | Service brakes: ABS / wheel speed sensor / tone ring |

A scan code and an open recall describing the same subsystem is the cheapest
finding available: **recall repairs are free regardless of age, mileage, or
ownership.** Have the VIN run before spending anything on a vacuum pump.

*Grounded in:* ODI **11750018**, which describes a brake booster vacuum pump
failure cascade — pedal going hard, ABS-like pulsing as the module tries to
compensate for falling vacuum.

**Watch for:** a pedal that feels harder than usual, especially on a cold start.

---

## Finding 4 — steering, and a reason not to buy a rack

`C056D` — **Power Steering Control Module Internal Failure** — **Confirmed**.
ODI **11328497** describes a complete loss of assist at low speed on this model,
which is a safety concern rather than a comfort one.

**Two things stop this from becoming an expensive repair.**

First, GM's own diagnostic guidance for this code is explicit: *if it is stored
only as a history DTC and is not present as a current DTC, do not replace the
module* — and check the harness for poor connections and corrosion before
condemning anything. That is the same Confirmed-versus-Not-Confirmed discipline
this repository already applies, coming from the manufacturer.

Second, there is a documented **software** fix for this presentation. GM bulletin
**PI1273** addresses a "Service Power Steering" message with `C056D` set by
**reprogramming the K43 Power Steering Control Module**, not by replacing
hardware.

> **`[verify]`** — PI1273 is written against the 2014 Silverado/Sierra. Whether
> it extends to the 2016 has not been checked. It is a question to put to a
> dealer, not an established fix for this truck.

**Do not let anyone sell you a steering rack off this code alone.** Re-scan
first: it is also a plausible downstream symptom of the same electrical event
that produced the network cluster below.

---

## The network cluster — nine codes, probably one event

`U0100` `U0101` `U0121` `U0140` `U0155` `U0164` `U0184` `U0422` `C0561`

Every one is **Not Confirmed**. Seven are "lost communication with \<module\>"
across modules that have nothing to do with each other.

Every module cannot independently lose the bus. **The bus went down as a unit** —
which is what a battery disconnect, a jump start, or a deep voltage sag looks
like in a code list. `B1000` (BCM memory error, Not Confirmed) fits the same
picture.

Expect most of these to disappear after a clear-and-re-scan. **Do not pay
anyone to chase them.**

---

## Emissions: NOT READY

All monitors complete **except EVAP**. The truck would **fail** an OBD-based
inspection today, not for an emissions fault but because a monitor hasn't run.

This is consistent with codes having been cleared recently — which is worth
noting on a truck bought seven weeks ago. **A cleared-code history is also how a
seller hides a check engine light**, so treat the clean modules with slightly
less confidence than usual until the re-scan.

---

## Triage summary

| Tag | Count | Meaning |
|---|---|---|
| **ACT** | 10 | Genuine finding worth diagnosis or a scheduled fix |
| WATCH | 3 | Unconfirmed but would matter if it recurred |
| minor | 1 | Real, cosmetic or convenience impact only |
| noise | 9 | Attributed to a single network/voltage event |

**23 codes reduce to three things worth money**, and two of them should be
priced only after a dealer runs the VIN for recalls and special coverage.

## Recommended next step: clear and re-scan

1. Have the VIN run for open recalls **and** special coverage programs.
2. Clear all codes.
3. Drive 1–2 weeks with several cold starts.
4. Re-scan.

Whatever returns **Confirmed** is real. The AFM misfire pattern will return if
it is lifters. Most of the network cluster will not.

Baseline for that comparison: [`../code-baseline.md`](../code-baseline.md).
