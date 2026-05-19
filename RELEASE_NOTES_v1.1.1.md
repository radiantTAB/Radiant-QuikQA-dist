# v1.1.1 — Radiant QuikQA evaluation build

**Released:** 2026-05-19
**Status:** Evaluation / testing use only — **not a medical device.**

## Changes since v1.1.0

- **Achieved max leaf speed is now reported as informational only.** The
  value still appears in the per-delivery PDF (in a greyed-out row next
  to the **nominal reference**) and in the per-leaf CSV for trending,
  but it no longer factors into the overall pass/fail verdict. The
  related CLI flags (`--no-speed-check`, `--speed-floor-action-mm-s`,
  `--speed-floor-tol-mm-s`) and the matching GUI controls have been
  removed. The per-leaf speed chart now draws the nominal speed as a
  dotted reference line instead of pass/fail thresholds.
- **Batch leaf-speed PDF now contains the full per-delivery analyses.**
  The first page is the existing batch summary (landscape); the full
  per-delivery analysis pages (metrics table + per-leaf RMS bar chart
  + speed chart + sample trajectories + error-vs-speed scatter) are
  now appended after it for every log, in input order — same content
  as each individual per-delivery PDF. Per-delivery PDFs are also
  still written separately in the output folder.

Per-delivery and per-leaf metric *calculations* are unchanged from
v1.1.0 — only the verdict-grading and report-shape changed.

## Assets

| File | Size | SHA-256 |
|---|---|---|
| `RadiantQuikQA.exe` | 102,761,258 B (~98 MB) | `2F57DAAAD1327B2E11817669F9F0A9FEF31AA7B11EF29F591FB85871AC0EA5A5` |
| `QuikQA Users Manual V 1.0.1.pdf` | ~754 KB | (manual unchanged) |

Verify the download (PowerShell):

```powershell
Get-FileHash RadiantQuikQA.exe -Algorithm SHA256
```

The .exe carries embedded PE version metadata — right-click →
*Properties* → *Details* should show **FileVersion 1.1.1.0** and
**CompanyName "Radiant Medical Physics Consulting LLC"**.

## Version note

The bundled manual is **V 1.0.1**; the binary is **v1.1.1**. The 1.0.1
manual remains accurate for every other module — the additions/changes
in 1.1.0 (TG-142 MLC leaf-speed module) and 1.1.1 (achieved-speed
demoted to informational; richer batch leaf-speed report) are not yet
documented in the PDF. A refreshed manual is in progress.

## SmartScreen / antivirus

The download is **unsigned**. Windows SmartScreen may warn *"Windows
protected your PC"* on first launch — click *More info* → *Run anyway*
if you trust the source. PyInstaller single-file executables sometimes
trigger antivirus false-positives because of how they self-unpack at
startup; this is a known PyInstaller pattern, not behavior in the
application.

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
anonymizer (or your own validated method) to de-identify any test data
first.

## Support

Email **tbernath@radiant-mpc.com**.

---

© 2026 Radiant Medical Physics Consulting LLC.
