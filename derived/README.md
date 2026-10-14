# H250/H350 derived corrections (N=1,600,000, seed 101)

This directory contains **postprocessed, versioned derivatives**, not replacement TPMC outputs. The original files under `results/` and the root `RESULT_MANIFEST.json`, `RESULT_INDEX.csv`, and `SHA256SUMS.txt` remain unchanged. Do not treat a retrospective validation file as an original completion record.

For the 166 directions at each of 250 and 350 km, use:

- [`TPMC_H250_H350_RESULT_RECONCILIATION_V2/REPROJECTED_COEFFICIENTS_AND_COMPONENTS.csv`](TPMC_H250_H350_RESULT_RECONCILIATION_V2/REPROJECTED_COEFFICIENTS_AND_COMPONENTS.csv) for direction-matched `Cd`, `Cl`, `Cs` and the reconstructed body/sailWall/solar force and moment components.
- [`TPMC_H250_H350_METADATA_COMPONENT_REPAIR_V1/INDEX.csv`](TPMC_H250_H350_METADATA_COMPONENT_REPAIR_V1/INDEX.csv) to find each case's corrected triangle metadata manifest and the SHA256 of its original triangle manifest, original labels, and derivative.
- The two directories' `README.md`, `AUDIT_REPORT.json`, and `SUMMARY.json` for methods, checks, and limitations.

The source Git blobs for `triangle_dataset_manifest.json`, `triangle_labels.csv`, `run_summary.json`, and `force_moment.json` were checked byte-for-byte against the local audited inputs for all 332 cases (1,328 blob comparisons, zero mismatches). The copied derivative package also passed 996 source/derivative SHA256 checks before publication.

The wind-axis convention changes `Cl` and `Cs` in exactly four pole cases (`a090_b090` and `a090_b270` at both altitudes). Force and moment triangle-to-total closure passed in 332/332 cases. The corrected per-case triangle manifest is an **overlay**: consumers must explicitly opt in and verify the SHA256 in `INDEX.csv`. Paths beginning `D:\TPMC\analysis\` inside copied audit records describe the analysis machine; in this repository, find the same files under `derived/` by their basename and case ID.

At 250 km, 26 original cases lack `completion.json` and `formal_ui_audit.json`; the derived retrospective checks do not fill or impersonate these records. The historical solver-source variants differ only in logging and metadata in the inspected files, but bitwise numerical equivalence is not asserted. This package does not repair frozen 450 km Formal V2 component metadata, which lacks matching 1.6M triangle labels. TPMC/SPARTA atmosphere comparison is out of scope.
