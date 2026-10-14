# H250/H350 metadata and component overlay V1

This directory is a **derived overlay**, not a replacement for original TPMC
outputs or the published TPMC-RESULT repository. No simulation was rerun and
no source file was edited.

For each of the 332 H250/H350 N=1,600,000 cases, `cases/<case_id>/` contains:

- `triangle_dataset_manifest.derived.json`: a copy of the original triangle
  manifest with the two erroneous `attitude_representation` values changed to
  `body_frame_incidence_direction`; `component_force` and `component_moment`
  are reconstructed from the original 3,244 triangle labels.
- `retrospective_validation.json`: a present-day, read-only evaluation of the
  original UI output contract. It includes the source-file hashes and an
  explicit `not_original_completion: true` marker.

`INDEX.csv` maps each case to the original triangle-manifest and triangle-CSV
SHA256 values and the derived-manifest SHA256. Consumers must opt in to this
overlay and verify those hashes; original sample/dataset manifests still refer
to the unmodified originals. Do not silently replace them.

Validation: 332/332 retrospective checks pass; 332/332 corrected manifests
pass independent source/copy hash checks. The geometry transform is identity
and the triangle freestream matches its manifest for all 332. Triangle Force
and Moment closure was established in the separate V2 reconciliation audit.

At 250 km, the original `completion.json` and `formal_ui_audit.json` are
absent for 26 cases. These historical records cannot be recovered or
backdated. The retrospective checks do not have the same provenance status.

The frozen 450 km Formal V2 production case outputs contain only case-level
JSON records and no matching 1.6M per-triangle labels. Earlier 400k labels
are not interchangeable. Thus this overlay does not repair 450 km component
forces or authorize a formal three-altitude component comparison.
