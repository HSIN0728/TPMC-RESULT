# Versioned derived audit packages (N=1,600,000, seed 101)

These are non-authoritative, versioned postprocessing and validation artifacts. They do not replace TPMC outputs under `results/`. `RESULT_INDEX.csv` and `RESULT_MANIFEST.json` remain unchanged; missing historical run records are never fabricated.

## H200/H300/H400 component and wind-axis overlay

See [`TPMC_H200_H300_H400_METADATA_COMPONENT_WIND_AXIS_REPAIR_V1/README.md`](TPMC_H200_H300_H400_METADATA_COMPONENT_WIND_AXIS_REPAIR_V1/README.md) and its `INDEX.csv`, `SUMMARY.json`, and `REPROJECTED_COEFFICIENTS_AND_COMPONENTS.csv`.

- 498/498 cases: triangle-force and triangle-moment closure passed.
- H200 source component metadata: 52/166 cases all-zero; the other 114/166 match triangle-label component sums.
- H300 and H400 source component metadata: 166/166 all-zero at each altitude; their reconstructed component values are provided only in the derived overlay.
- Wind-axis changes relative to the matching-direction H450 basis: two singular +Z/-Z cases each at H300 and H400; H200 axes already agree.

## H450 component metadata audit

See [`TPMC_H450_COMPONENT_METADATA_AUDIT_V1/README.md`](TPMC_H450_COMPONENT_METADATA_AUDIT_V1/README.md), `CASE_AUDIT.csv`, and `SUMMARY.json`.

- 166/166 cases: component metadata matches sums from the original triangle labels; force and moment closure passed.
- One original `tpmc/case_check.json` is missing for `20270301_h450_a000_b000_TPMC_N1600000_S101`; it was not recreated.

## H250/H350 derived corrections

See [`TPMC_H250_H350_METADATA_COMPONENT_REPAIR_V1/README.md`](TPMC_H250_H350_METADATA_COMPONENT_REPAIR_V1/README.md) and [`TPMC_H250_H350_RESULT_RECONCILIATION_V2/README.md`](TPMC_H250_H350_RESULT_RECONCILIATION_V2/README.md). These existing derivatives provide direction-matched coefficients and triangle-derived components; 26 missing historical H250 completion/audit records were not fabricated.

For every package, follow its case index and verify the recorded source hashes before use. Original files remain the authority for what was produced during each TPMC run. TPMC was not rerun to create these derivatives.
