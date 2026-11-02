# Data dictionary

## cube_results.csv – one row per cube set

| Column | Unit | Description | Source |
|---|---|---|---|
| cement | kg/m³ | Cement content of the matched mix design | D2 form |
| slag | kg/m³ | Slag content (0 for all mixes) | D2 form |
| fly_ash | kg/m³ | Fly ash content | D2 form |
| water | L/m³ | Maximum water content | D2 form |
| superplasticizer | L/m³ | Total admixture dosage (litres, not kg) | D2 form |
| coarse_agg | kg/m³ | Stone (20 mm + 14 mm, or 20 + 28 mm for CRCP), dry | D2 form |
| fine_agg | kg/m³ | Crusher sand + dune sand, dry | D2 form |
| design_slump_min / max | mm | Approved slump range of the mix | D2 form / mix design list |
| measured_slump | mm | Slump measured on site at sampling | Lab report |
| density | kg/m³ | Average cube density = mass / (length × width × 150 mm) | Lab report |
| age | days | Age at testing | Lab report |
| strength | MPa | Average compressive strength of the cube set | Lab report |
| mix_id | – | Matched mix design (e.g. AFR-30/20) | Matching |
| match | – | How the mix was matched: exact / class only / element (CRCP pavement) / description | Matching |
| flag | – | Data quality flag (kerb mix, impossible strength, cube spread, density) | Checks |
| date_cast | date | Date the concrete was cast | Lab report |
| lr | – | Lab request number (identifies the pour) | Lab report |
| swl | – | Lab job number | Lab report |
| spec | – | Specified strength class as written on the report | Lab report |
| supplier_report | – | Concrete supplier as written on the report | Lab report |
| element | – | Element / location description | Lab report |
| folder | – | Filing category: structure / element type | Filing |
| specified_slump_report | – | Specified slump as written on the report | Lab report |
| slump_check | – | Measured slump within / below / above the design range | Derived |
| cube1–3 | MPa | Individual cube strengths | Lab report |
| density1–3 | kg/m³ | Individual cube densities | Lab report |

## mix_designs.csv – one row per approved mix

mix_id, supplier, mix_class, binder and aggregate contents (as above), admixture_l, design_slump_min/max,
design_7d / design_28d (strength from the design trial), target (design target strength), d2_source.

## durability_results.csv – one row per durability test

| Column | Unit | Description |
|---|---|---|
| lr, swl, panel | – | Lab request, lab job and test panel numbers |
| structure, element_type, element | – | Where the concrete was placed |
| date_cast, age_days | date / days | Cast date and age at testing |
| opi_1–4, opi_mean | log scale | Oxygen permeability index per disk and mean (spec: > 9.3 full, 9.0–9.3 conditional, < 9.0 reject) |
| opi_cov | % | Variability of the permeability coefficient between disks |
| sorp_1–4, sorptivity_mean | mm/√h | Water sorptivity per disk and mean (spec: < 10) |
| porosity | % | Porosity from the sorptivity test |
| chloride_cond | mS/cm | Chloride conductivity (only results that look genuine) |
| chloride_reported_suspect | mS/cm | Chloride value on the report that appears copied (identical on 115 reports) |
| opi_judgement, sorp_judgement, overall | – | Judgement against the specification |
| flags | – | Data quality notes |
| report_date, source, file | – | Report date and file traceability |

## Specification references

- Strength: specified class (e.g. 30 MPa) at 28 days.
- Durability: Contract 305Q Vol 3, Table B6404/4 (exposure class XC4).
