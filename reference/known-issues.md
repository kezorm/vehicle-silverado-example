# Known Issues — GM 5.3L L83 / 8L90

> Vehicle fabricated; **the failure modes below are real and documented.** Each
> is marked **well-documented**, **moderately supported** or **anecdotal**.

---

## 1. AFM lifter failure — the finding that shapes the plan

**Well-documented.** Active Fuel Management shuts down four of the eight
cylinders under light load, using special switching lifters on **cylinders 1, 4,
6 and 7**. Those lifters collapse on command — and they also collapse when they
are not supposed to.

**The diagnostic signature is the cylinder set itself.** Misfire codes confined
to 1/4/6/7 with 2/3/5/8 clean point at lifters. Four coils do not fail
simultaneously, and if they did they would not choose exactly the AFM cylinders.

The Gen V L83 (2014–2018) improved oiling over earlier AFM engines but kept the
same switching-lifter architecture, and kept failing. AFM is reported as a large
share of L83 engine failures.

| | |
|---|---|
| Symptom order | Cold-start tick → intermittent misfire → CEL → rough running |
| Confirm with | Cylinder compression, or borescope the affected cylinders |
| Related codes | `P0300`, `P0301/4/6/7`, `P050D`, sometimes `P0521`, `P0016` |
| Cheap early check | Oil level and condition; AFM lifters are oil-pressure operated |

**Watch for:** a tick on cold start that disappears when warm. Owners
consistently report this *before* any code sets. If a pre-purchase inspection
note mentions it, that note is the earliest datapoint you will ever get — which
is why [the inspection invoice](../service/2026-05-20-pre-purchase-inspection/invoice.md)
records the technician's remark verbatim.

> **Which limit binds:** neither. This is condition-based, not scheduled. There
> is no interval to watch — only the symptom.

---

## 2. 8L90 transmission — shudder, and a temperature sensor pattern

**Well-documented.** The 8L90 8-speed drew widespread complaints for shudder and
harsh shifts. Separately, `P0700` + `P0711` (transmission fluid temperature
sensor circuit) appears repeatedly on this platform, with a wiring-harness
remedy.

`P0700` is not itself a fault — it is the engine module reporting that the
transmission module has a code. **Always read the TCM code behind it.**

> **A special coverage program may pay for this.** See
> [recalls-and-tsbs.md](recalls-and-tsbs.md) — and note it is `[verify]`,
> sourced from an owner complaint rather than a GM document.

---

## 3. Brake booster vacuum — an open recall and a documented failure

**Well-documented.** `C0299` (Brake Booster Large Vacuum Leak Detected) is set
by the electronic brake control module when booster vacuum is too low to assist
braking properly. Documented symptoms: hard pedal, longer stopping distances, a
hiss from the booster area.

**Recall `19V645000` covers vacuum power brake assist on 2014–2018 Silverado.**
A confirmed code and an open recall describing the same subsystem is the
cheapest finding available — recall work is free.

**Watch for:** a pedal noticeably harder than usual, especially on a cold start.

---

## 4. Power steering — check for a software fix before buying hardware

**Moderately supported.** `C056D` indicates an internal fault in the power
steering control module. GM's own guidance is explicit: *if it is stored only as
a history code and is not currently present, do not replace the module* — and
check the harness for poor connections and corrosion first.

GM bulletin **PI1273** addresses a "Service Power Steering" message with `C056D`
by **reprogramming** the module rather than replacing it.

> **`[verify]`** — PI1273 is written against the 2014 Silverado/Sierra. Whether
> it extends to 2016 has not been checked.

**Do not let anyone sell a steering rack off this code alone.**

---

## 5. Carbon buildup on intake valves — direct injection

**Moderately supported for this family.** Direct-injected engines do not wash
the back of the intake valve with fuel, so deposits accumulate. One complaint on
this platform (ODI **11220174**) records a dealer diagnosing carbon buildup on
cylinder 1 valves behind a `P050D`.

**Do not pre-emptively pay for a walnut blast** on the strength of DI's general
reputation. If rough cold idle, misfires or lean codes appear, borescope it then.

---

## Weakest claim on this page

**The special coverage program for the 8L90 harness.** Everything else here is
supported by manufacturer documentation, a recall campaign, or a consistent
pattern across multiple independent complaints. That one rests on a single
owner-submitted complaint citing a program number nobody has verified against a
GM document.

It is worth raising with a dealer precisely because the upside is large — a free
transmission harness — but it should not be planned around.
