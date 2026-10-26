# H250/H350 result reconciliation V2

This is a **derived, non-authoritative** audit of the existing 250 km and
350 km N=1,600,000 TPMC cases. No simulation was rerun and no source result
was overwritten. The TPMC/SPARTA atmosphere comparison is out of scope.

## Inputs and convention

- 332 cases from `D:\TPMC\data\cases\Av4_3244` (166 per altitude).
- Direction-matched wind axes from the frozen 450 km Formal V2 `run_summary.json`
  files. The frozen manifest SHA256 was verified as
  `d8ca55734304822848e65f5353d3ee6fe3ae37168abb231f5cfd9915f9592978`.
- Coefficients use the original body-frame force and each case's original
  `q_inf * A_ref`; only the projection basis changes. `Cs` is the stored `Cy`
  wind-side coefficient, not body-axis `Cy_body`.
- Components are sums of the original 3,244 triangle records grouped by
  `body`, `sailWall`, and `solar`, using `target_F*` and `raw_solver_M*`.

## Results

- Triangle force and both raw/derived moment sums match their case totals in
  **332/332** cases, within `rel_tol=1e-9`, `abs_tol=1e-12` in SI units.
- Component triangle counts are `body=1148`, `sailWall=1960`, `solar=136`
  in every case.
- Wind-axis reprojection changes exactly four cases: 250/350 km at
  `a090_b090` (+Z) and `a090_b270` (-Z). All other direction-matched axes
  agree with the 450 km reference.
- The original triangle manifests have `rotated_geometry` attitude metadata
  in 332/332 cases, while the case configs specify
  `body_frame_incidence_direction`. This audit flags but does not rewrite it.
- At 250 km, 26 cases have 10 output files and lack `completion.json` and
  `formal_ui_audit.json`; 140 have 12 files. At 350 km all 166 have 12.
- Source SHA groups: 250 km has 25 old and 141 new `TPMC/main.py` hashes;
  350 km has 166 new. The 26 missing-record cases are not identical to the
  25 old-SHA cases. The extra missing-record case is `a040_b120` at 250 km.
- The two exact `main.py` files differ only in console progress/executor
  logging; the two exact runner files differ only in output `particle_executor`
  metadata. This establishes a logging/metadata-only source diff, **not** a
  bitwise numerical reproducibility proof.

## Files

- `AUDIT_REPORT.json`: gate counts, case lists, source SHA inventory.
- `CASE_DETAILS.json`: complete per-case axes, components, totals, errors.
- `REPROJECTED_COEFFICIENTS_AND_COMPONENTS.csv`: compact analysis table.
- `MAIN_SOURCE_DIFF.patch`, `RUNNER_SOURCE_DIFF.patch`: exact source diffs.

## Limits

This derivative does not repair the 26 absent provenance files or the original
triangle-manifest metadata. The frozen 450 km Formal V2 source has only four
case-level result JSON files per case and no matching per-triangle labels;
therefore its component-force/moment zeros cannot be reconstructed from this
authority. Do not publish a three-altitude component comparison as formally
verified on the basis of this audit alone.
