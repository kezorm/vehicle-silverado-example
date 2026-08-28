# Recalls, Campaigns and Bulletins

Recall repairs are performed **free of charge** by any franchised dealer
regardless of vehicle age, mileage, warranty status, or whether you are the
original owner.

> The recall and complaint data on this page is **real**, retrieved from NHTSA's
> public API for the 2016 Chevrolet Silverado 1500 on 2026-08-27. Only the
> vehicle it is attached to is fabricated.

---

## The trap: a model-level lookup is not a VIN-level lookup

Querying NHTSA by make/model/year returns **11 campaigns** for a 2016 Silverado
1500. Reading each campaign's own scope statement, **fewer than half apply to an
ordinary 1500.**

| Campaign | Component | Applies here? |
|---|---|---|
| `19V645000` | Service brakes, hydraulic: **power assist: vacuum** | **Yes** — 2014-2018 Silverado |
| `19V761000` | Service brakes: ABS / wheel speed sensor / tone ring | **Yes** — 2014-2018 Silverado 1500 |
| `16V256000` | Suspension, front: control arm | **Yes** — 2016-2017 Silverado 1500 |
| `21V245000` | Seat belts, front | **Yes** — 2014-2016 Silverado 1500 |
| `21V504000` | Air bags: roof-rail inflator | **Yes** — 2015-2016 Silverado 1500 |
| `20V736000` | Air bags: side/window curtain inflator | **Yes** — 2015-2016 Silverado 1500 |
| `18V578000` | Service brakes: pedals and linkages | **No** — scoped to 2500/3500 and **Crew Cab Special Service / Police Pursuit** |
| `18V291000` | Seat belts, front | **No** — scoped to **Police Pursuit and Special-Service** vehicles |
| `16V651000` | Air bags: frontal | **No** — scoped to **2500 HD / 3500 HD**, Tahoe, Suburban |
| `17V437000` | Air bags: frontal | **No** — Buick LaCrosse, Spark EV, Caprice PPV, SS |
| `16V069000` | Service brakes: pedals and linkages | **`[verify]`** — summary says "1500, 2500, 3500 heavy duty"; ambiguous |

**Six clearly apply, four clearly do not, one is ambiguous from the summary
text alone.**

> **This is the single most reusable lesson on this page.** A model-level API
> tells you which campaigns *mention* your model. It cannot tell you whether
> your specific vehicle is in the affected production range, and it cannot tell
> you whether the remedy has **already been performed** on it. Only a VIN-level
> lookup does that.
>
> Check the VIN at **nhtsa.gov/recalls**, and have a dealer run it as well —
> dealers see campaigns and programs that NHTSA does not publish at all.

- [ ] Run the VIN at nhtsa.gov/recalls
- [ ] Have a dealer run the VIN for open campaigns **and special coverage**

Re-runnable queries:

```sh
curl "https://api.nhtsa.gov/recalls/recallsByVehicle?make=chevrolet&model=silverado%201500&modelYear=2016"
curl "https://api.nhtsa.gov/complaints/complaintsByVehicle?make=chevrolet&model=silverado%201500&modelYear=2016"
curl "https://vpic.nhtsa.dot.gov/api/vehicles/DecodeVinValues/<VIN>?format=json"
```

---

## The category NHTSA does not publish: special coverage

A **special coverage** (GM's term; other makers call them warranty extensions or
product improvement programs) is a manufacturer-funded repair beyond the normal
warranty. **They are not safety recalls, so they are not in NHTSA's database,
and no scan tool reports them.**

A complaint on this exact truck and transmission (ODI **11623044**) reports that
the `P0700` / `P0711` code pair was addressed under a GM special coverage
covering a **transmission wiring harness replacement**.

> **`[verify]` — this is the weakest claim on this page.** The program number
> appears in an owner-submitted complaint, not in a document from GM. It is a
> question to put to a dealer, not an established entitlement. Ask: *"are there
> any open special coverage programs, campaigns or bulletins against this VIN?"*

**The general rule matters more than this instance:** when a code has a known
pattern on a platform, check whether the manufacturer already decided to pay for
it before you do.

---

## Complaints — 795 on file

NHTSA complaints are public, citable by ODI number, and unusually honest,
because people file them when angry rather than when selling.

| Component | Complaints |
|---|---|
| Service brakes | 211 |
| Power train | 136 |
| Steering | 48 |
| Unknown or other | 45 |
| Electrical system | 38 |
| Engine | 33 |

**Read the brake number against the recall list.** 211 brake complaints
alongside two applicable brake recalls (`19V645000` vacuum assist, `19V761000`
ABS) is a coherent story, not a coincidence.

Complaints cited elsewhere in this record:

| ODI | Codes | Subject |
|---|---|---|
| 11750018 | `C0299` | Brake booster vacuum pump failure cascade — hard pedal |
| 11648955 | `P0700` `P0711` | 8L90 transmission fluid temp sensor |
| 11623044 | `P0700` `P0711` | Same, addressed under GM special coverage |
| 11502976 | `P0700` `P0796` | Transmission dropping gears at highway speed |
| 11480638 | `P050D` | Cold start rough running |
| 11342428 | `P0300` `P050D` | Sputtering, cutting out, CEL |
| 11330387 | `P0300` | Shudder / power loss, flashing CEL |
| 11290127 | `P050D` | Dealer diagnosed two fuel injectors |
| 11220174 | `P050D` | Dealer diagnosed carbon buildup on cylinder 1 valves |
| 11328497 | `C056D` | Complete loss of steering assist at low speed |

**A caution on reading complaint volume.** Complaints are self-selected. A high
count means many owners were angry enough to file, not that a fault is
universal — and a low count on a low-volume model is weak evidence of anything.
The Silverado sells in enormous numbers, so 795 complaints is a smaller *rate*
than it looks.
