# Case catalogs by particle count

Use these indexes to browse the TPMC cases by simulation particle count. They point to the existing case paths in `results/`; they do not relocate or duplicate the case data.

| Catalog | Cases | Coverage |
| --- | ---: | --- |
| `TPMC_N1600000_CASE_CATALOG_V1.csv` | 498 | 250, 350, and 450 km; 166 directions per altitude; geometry alias `Av4_3244` |
| `TPMC_N400000_CASE_CATALOG_V1.csv` | 1,182 | 250, 300, 350, 400, and 450 km |

The 400,000-particle catalog contains 166 cases at 450 km under `Av4_3244`. The other 1,016 cases use the existing `Av4_3244_old400000` geometry alias. Keep that alias as the geometry identifier; particle-count cohort is a separate classification. The `HISTORICAL_N400K_COHORT` label describes the 400k particle-count group and does not, by itself, declare its scientific results invalid.

Each row preserves the canonical `result_path`, geometry alias, case name, result status, file count, and byte count from the root `RESULT_MANIFEST.json`. To fetch a case, follow its `result_path`; do not infer a new folder path from the catalog filename.
