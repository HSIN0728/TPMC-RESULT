# H200/H300/H400 metadata/component/wind-axis derived repair V1

This is a non-authoritative derived overlay for 498 indexed N=1,600,000 cases. It does not replace or modify any original case output, index, manifest, checksum, or TPMC production data. TPMC was not rerun.

## What is corrected in the overlay

- `component_force` and `component_moment` are summed from the original 3,244 triangle labels, grouped as body=1148, sailWall=1960, solar=136. Force uses `target_Fx/Fy/Fz`; moment uses `raw_solver_Mx/My/Mz`.
- The original H200 component metadata is not uniformly zero: 52/166 cases have all-zero component metadata, while the other 114/166 match the triangle-label component sums. H300 and H400 have zero component metadata in 166/166 cases each.
- `Cd`, `Cl`, `Cy`/Cs and the wind-axis unit vectors are reprojected from the original case-level force with the original `q_inf * A_ref`, using the matching-direction H450 axes. Body-axis coefficients and force/moment outputs are unchanged.
- The stale attitude representation string is set to the value in each original `case_config_at_run.json`; source case checks pass and the recorded geometry transform remains the source transform.

## Validation and scope

- Source commit: `87bac1477c2d94c9cf4bcf2c93eb520dfe87b4be`.
- 498/498 cases have 3,244 unique triangle records and expected component counts.
- Triangle force, raw solver moment, and derived moment closure pass at `rel_tol=1e-09`, `abs_tol=1e-12` for every case.
- 498/498 original `case_check.json` records pass. Original completion/audit files are only recorded as present/absent; no historical records are fabricated.
- Wind-axis changes occur only in the two singular +Z/-Z directions at H300 and H400 (two cases per altitude). H200 axes already match the H450 reference.
- H450 provides 166 direction reference manifests and triangle-label files. One H450 `case_check.json` is missing; its case is listed in `SUMMARY.json` and no replacement is created.
- The earlier H250/H350 repair remains separately documented in `TPMC_H250_H350_METADATA_COMPONENT_REPAIR_V1` and `TPMC_H250_H350_RESULT_RECONCILIATION_V2`.

Use `INDEX.csv` to locate each derived manifest and verify the original-source hashes. Use the derived files only by explicit opt-in. Original files remain the authority for what was actually produced during each TPMC run.
