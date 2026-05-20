# v1.1.2 — Radiant QuikQA evaluation build

**Released:** 2026-05-19
**Status:** Evaluation / testing use only — **not a medical device.**

## Changes since v1.1.1

- **Setup → Clinics and Setup → Machines dialogs**: bumped the
  default and minimum heights so the Save bar at the bottom is
  visible without resizing. Machines: 740 → 900 default (min 780);
  Clinics: 920 → 1040 default (min 900).
- **Batch file picker** for the three tests that run over multiple
  deliveries (Leaf-Speed, VMAT Log, DICOM Anonymizer):
  - Pick a folder, get a sortable two-column file list (File name /
    Modified) of every `.bin` / `A*.dlg` (or `.dcm` for the
    anonymizer).
  - Click a column header to sort; click again to reverse.
  - Multi-select with Ctrl-click / Shift-click. Select all /
    Deselect all / Invert helper buttons. Live "N of M files
    selected" status line.
  - Only the checked files go into the batch; the rest are ignored.
  - For Leaf-Speed and VMAT Log, the picker auto-populates from the
    per-machine default log folder on machine switch.
  - For the Anonymizer, the picker is shown below the existing
    source/destination rows; when Source is a folder, only the
    picker-checked `.dcm` files are anonymized. Single-file Source
    behaviour is unchanged.
- **Engine support**: `analyze_leaf_speed_folder`,
  `analyze_vmat_log_folder`, `analyze_anonymize`, and `anonymize_path`
  each gain a `files: list[Path] | None = None` override. When
  provided, the explicit subset is used; when omitted, the existing
  folder-walk behaviour is preserved (no CLI changes required).

## Assets

| File | Size | SHA-256 |
|---|---|---|
| `RadiantQuikQA.exe` | 102,771,253 B (~98 MB) | `3BDA359023EB4A89210D4ADDD8B420B1EF21E149260B8806E2E598041CAEA474` |
| `QuikQA Users Manual V 1.0.1.pdf` | ~754 KB | (manual unchanged) |

Verify the download (PowerShell):

```powershell
Get-FileHash RadiantQuikQA.exe -Algorithm SHA256
```

The .exe carries embedded PE version metadata — right-click →
*Properties* → *Details* should show **FileVersion 1.1.2.0** and
**CompanyName "Radiant Medical Physics Consulting LLC"**.

## Version note

The bundled manual is **V 1.0.1**; the binary is **v1.1.2**. The 1.0.1
manual remains accurate for every other module — the additions in
1.1.0 (TG-142 MLC leaf-speed module), the 1.1.1 refinements
(achieved-speed informational; richer batch report), and the 1.1.2
UX improvements (taller setup dialogs, batch file picker) are not yet
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
decision-making, treatment planning, patient-care decisions,
dosimetric calibration, or machine release-to-service. All tolerances
and outputs must be independently reviewed and approved by a Qualified
Medical Physicist for your institution before any operational use.

Full terms: [LICENSE](https://github.com/radiantTAB/Radiant-QuikQA-dist/blob/main/LICENSE) · [DISCLAIMER](https://github.com/radiantTAB/Radiant-QuikQA-dist/blob/main/DISCLAIMER.md)

## Patient privacy

Do **not** send PHI when reporting issues. Use the in-app DICOM
anonymizer (or your own validated method) to de-identify any test data
first.

## Support

Email **tbernath@radiant-mpc.com**.

---

© 2026 Radiant Medical Physics Consulting LLC.
