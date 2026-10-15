# TPMC Results

這個 repository 只保存 TPMC Case 的結果，不保存 TPMC source、geometry 或 input。

## 結構

```text
results/<geometry_alias>/<case_name>/                 # existing layout for other geometry aliases
results/Av4_3244/N<particle_count>/<case_name>/       # Av4_3244 cases, grouped by particle count
└─ output/
   ├─ tpmc/
   └─ gnn_dataset/
```

每個 Case 另有 `result_manifest.json`；根目錄的 `RESULT_MANIFEST.json`、`RESULT_INDEX.csv` 與 `SHA256SUMS.txt` 用來查找與驗證結果。

`Av4_3244` case 依粒子數分在 `results/Av4_3244/N400000/` 與 `results/Av4_3244/N1600000/`；幾何 alias 仍是 `Av4_3244`。其他幾何 alias 保持原有目錄格式。

結果檔可直接下載或附加到 GPT 進行閱讀。原始 force/moment 以 Case 內的 `output/tpmc/force_moment.json` 與 `run_summary.json` 為準。

## 粒子數分類索引

按 1,600,000 與 400,000 粒子數查找 case，請使用 [`catalogs/particle_count/README.md`](catalogs/particle_count/README.md) 及其中兩份 CSV。索引保留每個 case 的原始 `result_path` 和 geometry alias，沒有搬動 case 資料夾。

## 多高度衍生稽核與後處理（N=1,600,000）

200/250/300/350/400/450 km 的 component、風軸與資料完整性衍生結果，請先看 [`derived/README.md`](derived/README.md)。衍生檔保留來源 SHA，**不是原始 TPMC 輸出的覆寫**。引用重投影係數或部件力／力矩時，請明確註明衍生版本與限制；缺失的歷史 completion、audit 或 case-check 紀錄均未補造。
