# TPMC result layout

`results/archive/legacy/Av4_3244/` contains historical TPMC uploads. They
remain byte-for-byte in Git history and were moved with `git mv`; no result
was deleted.

New publishable results should be placed under `results/<geometry_alias>/`.
The current authoritative body-frame S2 AERO database is maintained as the
versioned release package `body_frame_S2_v1.2`, not as a replacement for the
historical case archive.

Archive contents are retained for traceability and should not be used as the
current production database without checking each case manifest.
