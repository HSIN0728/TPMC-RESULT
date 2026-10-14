# Case catalogs by particle count

Use these indexes to browse the TPMC cases by simulation particle count. The Av4_3244 case folders are physically grouped under `results/Av4_3244/N400000/` or `results/Av4_3244/N1600000/`; the CSVs record those canonical paths.

| Catalog | Cases | Coverage |
| --- | ---: | --- |
| `TPMC_N1600000_CASE_CATALOG_V1.csv` | 498 | 250, 350, and 450 km; 166 directions per altitude; geometry alias `Av4_3244` |
| `TPMC_N400000_CASE_CATALOG_V1.csv` | 1,182 | 250, 300, 350, 400, and 450 km |

The 400,000-particle catalog contains 166 cases under geometry alias `Av4_3244` and 1,016 under the existing `Av4_3244_old400000` alias. Keep the geometry alias as the geometry identifier; particle-count cohort is a separate classification. The `HISTORICAL_N400K_COHORT` label describes the 400k particle-count group and does not, by itself, declare its scientific results invalid.

Each row preserves the canonical `result_path`, geometry alias, case name, result status, file count, and byte count from the root `RESULT_MANIFEST.json`. To fetch a case, follow its `result_path`; do not infer a new folder path from the catalog filename.
