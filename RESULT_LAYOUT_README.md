# TPMC-RESULT 結果路徑說明

## 目前 H450、N=1,600,000 資料

目前 `RESULT_INDEX.csv` 中有 166 個唯一的 H450、N=1,600,000 case。這 166 筆的 `result_path` 都指向 `results/Av4_3244/<case>` 舊扁平路徑；請以索引指定的路徑作為完整結果的查找位置。

同名資料夾也出現在 `results/Av4_3244/N1600000/<case>`。這些是較早且不完整的副本，不應視為完整結果：目前每個 H450 分組副本只有 5 個追蹤檔案，而索引所指向的扁平結果有 11 或 12 個檔案。請勿因資料夾名稱相同而以分組副本取代索引路徑。

## 手動查找 case

1. 在本儲存庫根目錄開啟 `RESULT_INDEX.csv`。
2. 依 `case_name` 欄搜尋完整 case 名稱。
3. 讀取該列的 `result_path`，並在儲存庫中開啟該路徑。
4. 若同一 case 另有其他路徑，仍以索引中的 `result_path` 為準；不要只依資料夾名稱或粒子數目錄推斷哪份資料完整。

例如，case `20270301_h450_a000_b000_TPMC_N1600000_S101` 的索引路徑是：

```text
results/Av4_3244/20270301_h450_a000_b000_TPMC_N1600000_S101
```

## 新舊路徑慣例

- 舊資料保留原位，不因路徑整理而搬移、覆蓋或刪除。
- v0.1.11 之後的新上傳採用分組路徑：`results/<geometry>/N<粒子數>/<case>`。
- 新舊路徑慣例不同時，查找個別 case 一律以 `RESULT_INDEX.csv` 的 `result_path` 欄為準。

本文件只說明路徑與查找方式；不更改 case 結果、`RESULT_INDEX.csv`、manifest 或 checksums。
