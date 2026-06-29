# Homeland Group — Consultant Selection Data

Data export and dashboard for the Homeland Group consultant selection pipeline
(Directory → Semi-Final → Comparison) across all projects.

Source workbook: **Consultant_Rate_Comparison_Homeland_Mohali** (Google Sheets),
exported on 2026-06-29.

## Contents

```
homeland-consultant-data/
├── README.md
├── consultant-dashboard.html      # Live dashboard (reads from the Google Sheet)
└── data/
    ├── source_sheet.md            # Full raw export of the workbook (all tabs)
    ├── 01_consultant_directory.csv    # Master directory: consultant × project tick matrix
    ├── 02_semifinal_pipeline.csv      # Semi-final pipeline: proposal / meeting / LOI / finalize
    ├── 03_local_architect_rates.csv   # Local architect ₹/sqft rate reference
    ├── 04_cost_DHARMAPUR.csv          # Cost comparison block — Dharampur (Vaana)
    ├── 05_cost_MULANPUR.csv           # Cost comparison block — Mulanpur (Infinia)
    ├── 06_cost_YPS.csv                # Cost comparison block — YPS (Leisure Valley)
    └── 07_cost_HLP.csv                # Cost comparison block — HLP
```

## Data notes

- **01_consultant_directory.csv** — One row per consultant. Columns 5+ are the ten
  projects, with `TRUE`/`FALSE` marking whether that consultant is shortlisted for the
  project. `Sr.no` and `Category` are only filled on the first row of each category
  group (as in the original sheet); blank means "same as the row above."
- **02_semifinal_pipeline.csv** — Consultants advanced to the semi-final stage, with
  boolean progress flags and a final `Finalize` decision.
- **Cost blocks (04–07)** — Per-project fee comparisons. Some projects compare several
  consultants side by side (e.g. Mulanpur has two rate/amount column pairs). Rates
  exclude GST. Empty cells mean "not costed yet."
- All figures are in INR (₹). `source_sheet.md` preserves the complete, unmodified export.

## Dashboard

`consultant-dashboard.html` is a live view that pulls the latest data from the Google
Sheet via a connector. It is included here for reference; the CSVs are the static
snapshot for version control.
