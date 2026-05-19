# v1.1.0 — Radiant QuikQA evaluation build

**Released:** 2026-05-19
**Status:** Evaluation / testing use only — **not a medical device.**

## Assets

| File | Size | SHA-256 |
|---|---|---|
| `RadiantQuikQA.exe` | 102,761,689 B (~98 MB) | `093958FBADF75F7DFB71DD8B28F24E07213DB01A88830F074A8E30485FC32F10` |
| `QuikQA Users Manual V 1.0.1.pdf` | ~754 KB | (text-only manual, no embedded screenshots) |

Verify the download (PowerShell):

```powershell
Get-FileHash RadiantQuikQA.exe -Algorithm SHA256
```

The .exe carries embedded PE version metadata — right-click →
*Properties* → *Details* should show **FileVersion 1.1.0.0** and
**CompanyName "Radiant Medical Physics Consulting LLC"**.

## New in 1.1.0

- **TG-142 MLC leaf-speed module** (log-based; no portal dosimetry
  required). Analyzes Varian TrueBeam trajectory logs (`.bin`) and iX
  dynalogs (`.dlg`) for:
  - per-leaf RMS positional error during dynamic delivery,
  - achieved leaf speed (graded as a floor vs. the programmed nominal),
  - max single-leaf error and error-at-speed,
  - beam hold-off count.
  Produces a 3-page PDF report, a per-leaf CSV, and a batch roll-up
  for a folder of logs. References: TG-142, MPPG 8.b, LoSasso 2008.
  Tolerances are configurable and must be approved by your QMP.

## Version note

The bundled manual is **V 1.0.1**; the binary is **v1.1.0**. The 1.0.1
manual remains accurate for every other module. A 1.1.0 manual update
is in progress.

## SmartScreen / antivirus

This build is **unsigned**. Windows SmartScreen may warn *"Windows
protected your PC"* on first launch — click *More info* → *Run anyway*
if you trust the source. PyInstaller single-file executables sometimes
trigger AV false-positives because of how they self-unpack; this is a
known PyInstaller pattern, not behavior in the application.

## Clinical disclaimer

This is an unvalidated analysis aid for **evaluation / testing only**.
It is **not** a medical device, has **not** been cleared by any
regulatory authority, and **must not** be used for clinical
decision-making, treatment planning, patient-care decisions, dosimetric
calibration, or machine release-to-service. All tolerances and outputs
must be independently reviewed and approved by a Qualified Medical
Physicist for your institution before any operational use.

Full terms: [LICENSE](https://github.com/radiantTAB/Radiant-QuikQA-dist/blob/main/LICENSE) · [DISCLAIMER](https://github.com/radiantTAB/Radiant-QuikQA-dist/blob/main/DISCLAIMER.md)

## Patient privacy

Do **not** send PHI when reporting issues. Use the in-app DICOM
anonymizer (or your own validated method) to de-identify any test
data first.

## Support

Email **tbernath@radiant-mpc.com**.

---

© 2026 Radiant Medical Physics Consulting LLC.
