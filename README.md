# Concrete Quality Control – Behaviour, Causes and Actions

A data science project on real concrete quality-control data from a road and bridge contract
(IRT Phase 2A, Cape Town). Cube strengths, slumps, densities, approved mix designs and
durability index results are combined to understand how the concrete behaved on site.

## Problem statement

Thousands of concrete tests are produced on a construction contract, but each result is usually
judged on its own (pass / fail). This project looks at all of them together to answer:

1. **Behaviour** – How does the concrete actually behave on site? (strength, variability, strength gain, slump, density, durability, trends)
2. **Why** – What explains that behaviour? (mix design, fly ash, slump / water, element type, time, testing)
3. **What can be done** – What practical actions and early-warning tools follow from it?

## Objectives

- Build a clean, documented dataset linking each cube set to its approved mix design.
- Describe strength, variability and durability by mix, element and over time.
- Test explanations with statistics, not assumptions.
- Produce practical recommendations (e.g. a 7-day early-warning threshold for 28-day failures).

## Data

| File | Rows | Description |
|---|---|---|
| `cube_results.csv` | 4,079 | One row per cube set (7 or 28 days etc.) with the matched mix design, slump, density |
| `mix_designs.csv` | 12 | Approved mix designs (D2 forms): cement, fly ash, water, admixture, aggregates, slump range |
| `durability_results.csv` | 198 | Durability index tests: oxygen permeability (OPI), water sorptivity, chloride conductivity |
| `cube_results_not_matched.csv` | 37 | Results that could not be matched to a mix design (kept for completeness) |

See `docs/data_dictionary.md` for every column.

**Confidentiality:** `data/raw`, `data/interim` and `data/processed` contain project identifiers
and are excluded from Git (see `.gitignore`). Only `data/anonymised` – created by
`notebooks/anonymise.ipynb` – may be shared publicly.

## Project structure

```
concrete-qc-305q/
├── data/
│   ├── raw/            original extracts (confidential – not in Git)
│   ├── interim/        intermediate files during cleaning
│   ├── processed/      final cleaned dataset used for analysis
│   └── anonymised/     safe to publish
├── notebooks/
│   ├── 00_setup_check.ipynb
│   ├── 01_data_understanding.ipynb   (step 1a)
│   ├── 02_data_cleaning.ipynb        (step 1b)
│   ├── 03_eda_behaviour.ipynb        (step 1c)
│   ├── 04_why.ipynb                  (step 2)
│   ├── 05_what_can_be_done.ipynb     (step 3)
│   └── anonymise.ipynb            (makes the safe-to-publish data)
├── reports/
│   └── figures/
├── docs/
│   └── data_dictionary.md
└── README.md
```

## Project plan

| Step | Notebook | Status |
|---|---|---|
| 0 – Setup | `00_setup_check` | Done |
| 1a – Data understanding | `01_data_understanding` | Done |
| 1b – Data cleaning | `02_data_cleaning` | Done |
| 1c – EDA: behaviour | `03_eda_behaviour` | Done |
| 2 – Why | `04_why` | Done |
| 3 – What can be done | `05_what_can_be_done` | Done |

## Author

Sibahle Vathu – Materials Technician and aspiring data scientist.
