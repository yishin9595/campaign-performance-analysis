# Channel Campaign Performance Analysis

多渠道廣告成效分析：評估各月份、渠道與 campaign 的投放效率，並提出後續預算配置建議

## 專案背景

本專案分析 2025–2026 年多渠道廣告活動資料，從月度、渠道與 campaign 分析點擊、轉換與營收表現，並回答以下問題：

- 2026 年相較於 2025 年，整體廣告成效如何變化？
- 哪些月份同時具備高營收與高投放效率？
- 哪些渠道帶來較好的點擊與轉換效率？
- 哪些 campaign 為成功案例，哪些應優先優化？

## 核心發現

1. **整體投放效率下滑**：2026 年花費只增加 0.65%，但 Revenue 下降 12.92%、ROAS 下降 13.48%、CPA 上升 6.68%。
2. **2025-05 為高營收、高效率月份**：Email 只占該月花費約 4.15%，卻貢獻約 71.55% 的營收。不過 Email 主要是寄給既有客戶，成本計算方式也可能與其他渠道不同，實際貢獻可能被高估，需透過增量測試驗證。
3. **`case-study-promo` 為成功案例**：在 2025-05 同時具備高 CVR、低 CPA 與高 ROAS，適合拆解其素材、受眾與落地頁策略。
4. **2026-09 的低效率集中在 Display 渠道**：其中 `developer-outreach` 活動是主要拖累來源。

## 資料來源

本專案使用公開的 Sample Marketing Campaigns CSV Dataset：

- [資料集介紹頁](https://csvtodashboard.com/sample-marketing-csv)
- [1,000 rows CSV](https://csvtodashboard.com/datasets/marketing-1000.csv)

## 分析架構

### 1. Overall Performance Trend

觀察各月份與年度的 Revenue、Spend、Conversions 等指標變化，並比較 2025 與 2026 的年度表現。

### 2. Channel Performance

比較不同渠道的營收貢獻、花費、點擊率與轉換效率。

### 3. Campaign Performance

找出高效率與低效率的 campaign，特別關注高 Spend、低 ROAS 的情況。

### 4. Campaign × Channel Analysis

交叉分析 campaign 與 channel，確認低效率是來自渠道本身還是特定活動，作為後續預算與素材測試的依據。

## 指標定義

| 指標 | 定義 | 判斷方向 |
| --- | --- | --- |
| CTR | clicks / impressions | 越高代表素材越能吸引點擊 |
| CVR | conversions / clicks | 越高代表點擊後的流量品質或轉換流程越好 |
| CPA | spend / conversions | 越低越好，代表取得一次轉換的成本越低 |
| ROAS | revenue / spend | 越高越好，代表每花一元廣告費帶回越多營收 |
| Spend | 廣告花費 | 投放規模 |

## 主要分析結果

### 年度比較：預算幾乎持平，但營收與轉換效率下降

2026 年 CTR 略微提升，但 CVR、Conversions 與 Revenue 皆下降，代表廣告仍能吸引點擊，問題可能出在點擊後的轉換環節，例如流量品質、落地頁或轉換流程。

<img width="414" height="225" alt="2025 與 2026 年度指標比較表" src="https://github.com/user-attachments/assets/8d33f0a5-ae92-49f6-9664-79ccd63405c2" />

### 每月趨勢

<img width="962" height="380" alt="每月 Revenue、Spend 與 Conversions 趨勢圖" src="https://github.com/user-attachments/assets/f2bf7d62-80ac-4657-82a6-4ad683f54536" />
<img width="947" height="535" alt="每月 ROAS 與 CPA 趨勢圖" src="https://github.com/user-attachments/assets/9e61a930-b765-4bd1-a59b-d92eae94517a" />

- **2025-05 表現最佳**：整體 ROAS 為 45.94x，較 2025 年平均高約 28%，CPA 為 3.23。
- **2026-09 表現最弱**：整體 ROAS 為 18x，較 2026 年平均低約 42%，CPA 上升至 6.17。

### 2025-05 Channel & Campaign 成效

<img width="1034" height="201" alt="2025-05 各渠道成效表" src="https://github.com/user-attachments/assets/80c3745a-7515-4968-9c82-d96f2feade04" />
<img width="1080" height="315" alt="2025-05 各 campaign 成效表" src="https://github.com/user-attachments/assets/b95fb122-15fd-416b-9817-78ad696a4e8f" />

- **Email 渠道表現最突出**：以極低的花費帶來大部分營收，但由於 Email 多觸及既有客戶，建議先透過增量測試確認其實際貢獻，再小幅增加預算，觀察邊際 ROAS 能否維持。
- **`case-study-promo` 活動表現最佳**：CVR 為 8.87%，CPA 只有 1.07，ROAS 達 161.81x，代表使用者點擊後的轉換效率很高，建議將其素材、受眾設定與落地頁作為參考範本，套用到其他活動的優化上。

### 2026-09 Channel & Campaign 成效

<img width="2056" height="409" alt="2026-09 各渠道成效表" src="https://github.com/user-attachments/assets/8b6c571e-ffaa-491f-b64c-35e7314dd00c" />
<img width="2148" height="745" alt="2026-09 各 campaign 成效表" src="https://github.com/user-attachments/assets/8101fd24-444b-45c3-9338-6dfe54ac55cc" />
<img width="2204" height="803" alt="2026-09 渠道 x campaign 成效表" src="https://github.com/user-attachments/assets/2c2cd9d5-551e-43ac-ae87-ee316df31abb" />

- **Display 渠道是主要拖累**：ROAS 只有 0.56x，CPA 為 159.64，投入成本尚未回收。
- **問題集中在 `developer-outreach` 活動**：其 ROAS 同樣為 0.56x、CPA 為 159.98，且 Display 整個渠道都表現不佳，該活動轉換數雖然只有 12 次，但與整體水準差距過大，建議先降低預算。

## 商業建議

1. **驗證 Email 的實際貢獻**：Email 多寄給既有客戶，部分購買即使不寄信也會發生，因此報表上的營收可能被高估。建議將客戶隨機分為寄信組與不寄信組，比較兩組的購買差異，確認 Email 真正帶來的額外營收，再決定是否擴大投入
2. **Display 渠道整體表現不佳**：需要先降低預算，並檢查渠道內的活動素材、版位、受眾與落地頁，同時確認追蹤與歸因設定是否正常
3. **複製 `case-study-promo` 的成功經驗**：拆解其素材、受眾與轉換流程，測試能否在其他活動中也有相同優秀表現。


## 使用工具

- Python
- pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook

## 專案檔案

- [Campaign_Performance_Analysis.ipynb](./Campaign_Performance_Analysis.ipynb)
