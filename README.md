# TPMC Results

這個 repository 只保存 TPMC Case 的結果，不保存 TPMC source、geometry 或 input。

## 結構

```text
results/<geometry_alias>/<case_name>/
└─ output/
   ├─ tpmc/
   └─ gnn_dataset/
```

每個 Case 另有 `result_manifest.json`；根目錄的 `RESULT_MANIFEST.json`、`RESULT_INDEX.csv` 與 `SHA256SUMS.txt` 用來查找與驗證結果。

結果檔可直接下載或附加到 GPT 進行閱讀。原始 force/moment 以 Case 內的 `output/tpmc/force_moment.json` 與 `run_summary.json` 為準。
