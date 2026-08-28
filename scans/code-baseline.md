# Diagnostic Code Baseline

> **⚠️ FABRICATED SCAN.** See
> [`2026-06-18/analysis.md`](2026-06-18/analysis.md) for exactly what is
> invented and what is real. Every code number and description below is a real,
> standard DTC; the invented part is that they appeared together on one truck.

All **23** codes from the 2026-06-18 scan (118,050 mi).
This is the baseline against which every future scan is compared.

Machine-readable copy: [`2026-06-18/codes.json`](2026-06-18/codes.json)

## Triage key

| Tag | Meaning |
|---|---|
| **ACT** | Genuine finding worth diagnosis or a scheduled fix |
| WATCH | Unconfirmed but would matter if it recurs — check on next scan |
| minor | Real fault, cosmetic or convenience impact only |
| noise | Attributed to a single network/voltage event; expected to clear |

**Distribution:** ACT 10 · WATCH 3 · minor 1 · noise 9

## ENGINE (ECM)

| Code | Status | Triage | Description |
|---|---|---|---|
| `P050D` | Confirmed | **ACT** | Cold Start Rough Idle |
| `P0300` | Confirmed | **ACT** | Random/Multiple Cylinder Misfire Detected |
| `P0301` | Confirmed | **ACT** | Cylinder 1 Misfire Detected |
| `P0304` | Confirmed | **ACT** | Cylinder 4 Misfire Detected |
| `P0306` | Confirmed | **ACT** | Cylinder 6 Misfire Detected |
| `P0307` | Confirmed | **ACT** | Cylinder 7 Misfire Detected |
| `P0521` | Not Confirmed | WATCH | Engine Oil Pressure Sensor/Switch Range/Performance |
| `P0016` | Not Confirmed | WATCH | Crankshaft Position - Camshaft Position Correlation, Bank 1 Sensor A |

## TRANSMISSION (TCM)

| Code | Status | Triage | Description |
|---|---|---|---|
| `P0700` | Confirmed | **ACT** | Transmission Control System Malfunction |
| `P0711` | Confirmed | **ACT** | Transmission Fluid Temperature Sensor 'A' Circuit Range/Performance |
| `P2723` | Not Confirmed | WATCH | Pressure Control Solenoid 'D' Stuck Off |

## ELECTRONIC BRAKE CONTROL (EBCM)

| Code | Status | Triage | Description |
|---|---|---|---|
| `C0299` | Confirmed | **ACT** | Brake Booster Large Vacuum Leak Detected |
| `C0561` | Not Confirmed | noise | System Disabled Information Stored |

## POWER STEERING (PSCM)

| Code | Status | Triage | Description |
|---|---|---|---|
| `C056D` | Confirmed | **ACT** | Power Steering Control Module Internal Failure |

## BODY CONTROL (BCM)

| Code | Status | Triage | Description |
|---|---|---|---|
| `U0422` | Not Confirmed | noise | Invalid Data Received From Body Control Module |
| `B1000` | Not Confirmed | minor | Electrically Erasable Programmable Read Only Memory Error |

## NETWORK

| Code | Status | Triage | Description |
|---|---|---|---|
| `U0100` | Not Confirmed | noise | Lost Communication With ECM/PCM 'A' |
| `U0101` | Not Confirmed | noise | Lost Communication With TCM |
| `U0121` | Not Confirmed | noise | Lost Communication With Anti-Lock Brake System Control Module |
| `U0140` | Not Confirmed | noise | Lost Communication With Body Control Module |
| `U0155` | Not Confirmed | noise | Lost Communication With Instrument Panel Cluster Control Module |

## RADIO

| Code | Status | Triage | Description |
|---|---|---|---|
| `U0184` | Not Confirmed | noise | Lost Communication With Radio |

## HVAC

| Code | Status | Triage | Description |
|---|---|---|---|
| `U0164` | Not Confirmed | noise | Lost Communication With HVAC Control Module |

## Modules scanned clean

- SDM (airbag/restraints)
- OnStar / telematics
- Tire pressure monitor
- Instrument cluster
- Transfer case

**Emissions readiness:** NOT READY - EVAP monitor incomplete; all others complete

---

## How to use this on the next scan

1. Save the new report under `scans/YYYY-MM-DD/`.
2. Run `bin/extract-text` to write the `.txt` extraction beside the PDF.
3. Compare the new code list against this table.
4. Codes that **disappeared** were debris — confirmed as noise.
5. Codes that **persist as Confirmed** are real and worth money to fix.
6. Codes that are **new** deserve attention regardless of tag.

The value of this folder is the diff, not any individual report. A single scan
showing 23 codes is nearly uninterpretable; a second scan taken
after clearing them turns the same list into a short, trustworthy work order.
