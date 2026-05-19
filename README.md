# Radiant QuikQA — Public Evaluation Release

> ⚠ **Evaluation / testing use only — not a medical device.** Radiant
> QuikQA is an unvalidated analysis aid. It has not been cleared,
> approved, or registered as a medical device, and must not be used
> for clinical decision-making, treatment planning, patient-care
> decisions, dosimetric calibration, or machine release-to-service.
> All tolerances and outputs must be independently reviewed and
> approved by a Qualified Medical Physicist for your institution
> before any operational use. See [`LICENSE`](LICENSE) and
> [`DISCLAIMER.md`](DISCLAIMER.md). **Do not transmit PHI** through
> this software or to any third party.

A PyLinac-powered Windows QA tool for radiation oncology physics:
Winston-Lutz, Picket Fence, VMAT (DRGS / DRMLC), **TG-142 MLC
leaf-speed** (log-based), TG-51 photon and electron dosimetry, DICOM
anonymizer, and a PDF tools suite. Standalone single-file `.exe`; no
install required.

## Download

Latest evaluation build: see the [Releases page][rel].

[rel]: https://github.com/radiantTAB/Radiant-QuikQA-dist/releases/latest

- **`RadiantQuikQA.exe`** — single-file Windows app (~98 MB)
- **`QuikQA Users Manual V 1.0.1.pdf`** — user manual (see version note below)

## Verifying the download

After downloading, confirm the SHA-256 matches the value on the release
page (PowerShell):

```powershell
Get-FileHash RadiantQuikQA.exe -Algorithm SHA256
```

The .exe carries embedded version metadata: right-click →
*Properties* → *Details* should show **FileVersion 1.1.0.0** and
**CompanyName "Radiant Medical Physics Consulting LLC"**.

## System requirements

- Windows 10 / 11, 64-bit
- ~250 MB free disk for PyInstaller's first-launch unpack cache
- No installer — double-click `RadiantQuikQA.exe`

## SmartScreen / antivirus

The download is **unsigned**. Windows SmartScreen may warn *"Windows
protected your PC"* on first launch — click *More info* → *Run anyway*
if you trust the source. PyInstaller single-file executables
occasionally trigger antivirus false-positives because of how they
self-unpack at startup; this is a [known
pattern](https://pyinstaller.org/en/stable/common-issues-and-pitfalls.html#anti-virus-false-positives),
not behavior in the application itself.

## Version note

The bundled manual is **V 1.0.1**; the binary is **v1.1.0**. The 1.0.1
manual remains accurate for every other module (Winston-Lutz, Picket
Fence, VMAT, TG-51, anonymizer, PDF tools, etc.). The single addition
in 1.1.0 that the manual does not yet describe:

- **TG-142 MLC leaf-speed module** — log-based (`.bin` trajectory logs
  / `.dlg` dynalogs). Reports per-leaf RMS positional error, achieved
  leaf speed (as a floor vs. the programmed nominal), max single-leaf
  error, error-at-speed, and beam hold-offs. PDF report + per-leaf CSV
  + batch roll-up.

A 1.1.0 manual update is in progress.

## License and clinical disclaimer

By downloading or using this software you agree to the
[`LICENSE`](LICENSE) (proprietary, evaluation use only — no clinical
use, no redistribution, no warranty) and the
[`DISCLAIMER.md`](DISCLAIMER.md). The defaults shipped in the
configuration are convenience starting points (TG‑142 / MPPG / vendor
ranges) — **not** an endorsement that those values are appropriate for
your linac, your detector, your beam data, or your institutional
protocol.

## Reporting issues

Email **tbernath@radiant-mpc.com** with:

- a description of the behavior,
- the version (right-click `RadiantQuikQA.exe` → *Properties* →
  *Details* — should read **1.1.0.0**),
- only if relevant and **fully de-identified**, minimal reproduction
  data.

**Do not send PHI.** Use the in-app DICOM anonymizer (or your own
validated method) to de-identify before sharing.

## What's the relationship between this repo and the source?

This repo is **distribution only** — public README, license,
disclaimer, manual, and release binaries. The source for Radiant
QuikQA is **not** published; it remains the proprietary work of
Radiant Medical Physics Consulting LLC. See the `LICENSE` for what you
may and may not do with the binary.

---

© 2026 Radiant Medical Physics Consulting LLC.  
[radiant-mpc.com](https://radiant-mpc.com)
