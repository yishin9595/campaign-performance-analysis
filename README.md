# Campaign Performance Analysis

## 商業問題

為不同產業的客戶規劃下一波投放策略，各客戶總預算不變的前提下，提升 ROAS 且轉換數不減少，各產業該加碼、減碼哪些組合？

- 主要指標：ROAS（營收 / 廣告花費）
- 護欄指標：轉換數
- 後台可調整：平台、素材格式、裝置
- 依產業分開檢查：同一個建議在不同產業可能不同，因此每個結論都會拆開產業確認是否成立

## 整體主要發現

只分析 Conversions 型廣告（2,946 筆），整體 ROAS 為 8.01。

1. 約 52% 的預算投放在 Mobile，但 Mobile 的 ROAS 只有 4.68，低於整體水準，Desktop 為 13.36，差距主要來自 CVR 轉換率（0.0867 vs 0.0323）。
2. Facebook 的 ROAS 最高（14.19），主因是 CPC 低；Google Ads 與 LinkedIn CPC 高，ROAS 偏低，這個結果在每個產業都成立。
3. 素材格式的影響較小（各素材 ROAS 差約 1.4 倍，平台與裝置約 3 倍），且最佳素材因產業而異。

以上結論若改用單筆 campaign ROAS 的中位數，以及將 2024、2025 年分開比較，結果都一致。

## 建議

| 建議 | 預期效果（保守估算） | 信心 |
|---|---|---|
| 將約 10% 的 Mobile 預算移到 Desktop | 營收至少增加約 510 萬，轉換數增加約 1.1 萬筆 | 高 |
| 將約 10% 的 Google Ads 預算移到 Facebook | 營收至少增加約 234 萬，轉換數增加約 4,400 筆 | 高 |
| 素材依產業選擇 | 影響較小 | 中 |
| Finance 客戶小額測試 Twitter | 優勢存在但被少數 campaign 放大 | 中 |

預期效果以加碼後效率最差的情況估算，建議先以 2 成預算測試幾週，確認效果後再擴大。

## 分析流程

1. **定義問題**：確認商業問題、主要與護欄指標，並拆成 4 個子問題，每個子問題先寫下假設
2. **資料理解**：檢查欄位、缺值與樣本數，決定只分析 Conversions 型廣告
3. **建立基準線**：以「總營收 / 總花費」計算整體 ROAS
4. **回答子問題**：平台、素材、裝置各自比較，再依產業拆開檢查；並將 ROAS 拆解為「每筆轉換價值 × 轉換率 / 點擊成本」找出勝出原因
5. **檢查加碼後的變化**：依花費分級，觀察 ROAS 與 CPA 是否隨花費上升而變差
6. **驗證結論**：營收集中度、單筆 ROAS 中位數、2024、2025 跨年度比較
7. **提出建議**


## 資料來源

[Digital Advertising Campaign Performance Dataset](https://www.kaggle.com/datasets/juniornsa/digital-advertising-campaign-performance-dataset)（Kaggle）

## 研究工具

- Python（pandas、NumPy、Matplotlib）
- Jupyter Notebook

## 分析結果

[Campaign Performance Analysis](./Campaign_Performance_Analysis.ipynb)
