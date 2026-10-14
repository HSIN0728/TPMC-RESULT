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

## 250/350 km 衍生修正（N=1,600,000）

250 與 350 km 的風軸係數、部件力／力矩及姿態 metadata 事後修正，請從 [`derived/README.md`](derived/README.md) 開始閱讀。它們是保留來源 SHA 的獨立衍生版本，**不是原始 TPMC 輸出的覆寫**。引用 Cl、Cs 或部件力時，請明確標示使用衍生版本及其限制；26 個 250 km case 缺少的原始 completion／audit 紀錄並未補造。
