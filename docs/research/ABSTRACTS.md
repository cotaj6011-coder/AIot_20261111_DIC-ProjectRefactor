# A–F Abstracts — New Taipei Research Proposal

**Scope:** These abstracts describe the proposed New Taipei roadside study, using the original proposal and DESIGN.md as sources. Sample and Phase 2 results are reported as distinct experiments.

## 中文摘要（約 300 字；A–F 對應）

舊金山SFpark試辦區自陳尋位時間由11分36秒降為6分36秒（43%），反映尋位成本值得改善；此為資訊與定價整體案例，非本專題成效（A）。但即時有位不保證抵達有位，延遲、缺漏及來源故障仍會誤導決策（B）。本研究規劃新北路邊停車代理，自動取數、檢查品質並依抵達時間推薦（C）。以Persistence、隨機森林及直方圖梯度提升預測，結合風險排序、有界重試、重規劃與棄權（D）。採60/20/20時間切分、排除跨界標籤，評估誤差、校準、Top-3成功率及故障處理（E）。既有文件記載Persistence的MAE為0.3268格，整體優於兩種樹模型；本庫未重現。預期建立可追溯決策流程，推薦與代理效益待驗證（F）。

**字數與來源：**正文 307 個非空白 Unicode 字元；移除六個「（A）–（F）」標記後為 289 個字元，計入標點、數字與英文字母。SFpark 數字為平日 09:00–18:00 的外部試辦前後自陳結果；對照區同期下降 13%，不能將 43% 當成本專題目標、因果效果或新北實測。[S1：SFMTA 評估摘要，印刷頁 12–13](https://www.sfmta.com/media/11985/download?inline=)。MAE 來源為 [DESIGN.md §10–11](../../DESIGN.md)。

## IEEE-style English abstract (proposal, not completed results)

**Title—**An Uncertainty-Aware AI Agent for Arrival-Time Parking Availability Prediction and Risk-Aware Recommendation

**Abstract—**In San Francisco's SFpark pilot areas, reported parking-search time fell from 11 minutes 36 seconds to 6 minutes 36 seconds, a 43% decrease, under a combined information and pricing program. This external case motivates attention to search costs; it is not an outcome of the proposed system. A vacancy observed at query time may disappear before arrival, while delayed observations and source failures further complicate guidance. This study proposes an evidence-aware smart parking agent for roadside segments in New Taipei City, Taiwan. Its workflow autonomously collects source data, validates schema, freshness and capacity, compares Persistence, Historical Median, Random Forest and HistGradientBoosting, and produces arrival-time Top-k recommendations with candidate-specific evidence. A planner coordinates tool selection, bounded retry, replanning and abstention rather than asking a language model to invent availability. A chronological 60/20/20 evaluation with purged cross-boundary targets is planned to assess prediction error, fullness-risk calibration, arrival-time Top-3 success, coverage and fault handling against matched baselines and a fixed pipeline. A separate source design reports offline MAEs of 0.3268 for Persistence, 0.4027 for Random Forest and 0.5375 for HistGradientBoosting. These results favor Persistence in that aggregate comparison, are not independently reproduced in this repository, and require corrected temporal-boundary validation. Arrival-time recommendation benefits and agent superiority remain unverified. The intended contribution is a falsifiable integration of data provenance, decision-time risk assessment and failure-aware orchestration, with explicit limits on unsupported recommendations.

**Index Terms—**Smart parking, arrival-time prediction, AI agent, data quality, uncertainty-aware recommendation, intelligent transportation systems.

## 完整 A–F 論述（作業頁可直接對照）

### A. Attention Getter｜可量化的尋位痛點

駕駛要找的是抵達時仍可停放的車位。SFMTA 的 SFpark 試辦評估顯示，試辦區平日 09:00–18:00 自陳尋位時間由 **11 分 36 秒降為 6 分 36 秒，下降 43%**；對照區則下降 **13%**。這項舊金山「停車資訊＋需求反應定價」整體案例直接呈現尋位成本，但不能推論新北有相同尋位時間，也不能將改善歸因於本專題或 AI。研究因此聚焦「查詢時有位，抵達時是否仍有位」，而非宏觀市場規模。[S1](https://www.sfmta.com/media/11985/download?inline=)

### B. But｜從尋位成本接到決策缺口

即時車位顯示只能描述觀測當下；在行車期間，需求變動、資料延遲與來源故障可能使建議失效。Cao 等人的路邊停車研究亦討論不準確預測把駕駛導向已占用車位、延長搜尋的問題。現有研究已涵蓋時空預測與不確定性，因此本專題的缺口是：在新北路邊情境中，預測、資料品質與失敗處理是否共同改善**抵達決策**，須以同條件基準驗證，而非宣稱首創停車預測。[6](https://doi.org/10.1016/j.tra.2025.104391) [11](https://doi.org/10.3390/s25113463)

### C. Cure｜主動取數、分析與決策的 Agent

規劃智慧停車 AI Agent：接收目的地、抵達時間與步行限制後，Planner 自動選工具、擷取資料、檢查品質、呼叫預測與排序工具，再輸出含來源時間、依據及限制的 Top-k 建議。來源逾時或失效時有界重試／重規劃；證據不足則退回合法基準、要求確認或棄權。語言互動負責理解與協調，車位數與風險依工具結果產生；**新北整合服務仍為規劃**。[原始設計 §1–6](../../DESIGN.md)

### D. Development｜三類具體方法與工作流

方法分為三類：（1）**情境與資料取得**：Planner 選擇 HTTP JSON Connector／歷史 JSONL，檢查 schema、來源時間、缺值及容量。（2）**時間預測與風險分析**：以 past-only lag／rolling 特徵比較 Persistence、同星期同時段 Historical Median、Random Forest、HistGradientBoosting；規劃以 Isotonic／Platt scaling 校準，未驗證前不把品質分數當滿位機率。（3）**決策與自主調度**：先套用停車類型／步行限制，再以距離、經驗證的滿位風險及各候選自身品質作規則排序，並透過 Tool Registry＋Planner 執行有界 Retry／Replan／Abstain、保存 Evidence Log。GIS 呈現參照來源中臺中原型的 React／TypeScript／Leaflet 與 FastAPI，新北尚未整合；Haversine 僅為直線距離估計。六步工作流及失敗分支統一見 [AGENT_WORKFLOW.md](AGENT_WORKFLOW.md)。[原始設計 §3–6、§10、§12–13](../../DESIGN.md)

### E. Experiments｜與假設一一對應的驗證

規劃依時間順序 **60／20／20** 切分，排除目標時間跨切分邊界的樣本，僅使用 cutoff 前可得特徵。H1 在共用 test rows 與 +30／+60 分鐘 horizon 比較模型及 Persistence 的 MAE／RMSE；H2 在相同步行限制及接受請求覆蓋率下，比較風險排序與距離排序的抵達 Top-3 Success、Brier／ECE 與棄權率；H3 以相同工具及 timeout／stale／schema error 故障，比較 Agent 與固定 Pipeline 的無證據建議、coverage 及 p95 延遲。MAE 改善至少 5%、滿位 Recall ≥0.80、Top-3 改善至少 5 個百分點、p95 ≤3 秒均為**待驗證門檻**。[評估規劃](INTRODUCTION.md)

### F. Findings｜已知證據、預期貢獻與限制

來源 DESIGN.md 記載新北 Phase 2 在同一批 9,178,935 筆測試觀測上的 MAE：Persistence **0.326757**、Random Forest **0.402669**、HistGradientBoosting **0.537539**。這項整體比較**不支持樹模型優於 Persistence**，且有跨切分標籤與觀測涵蓋限制，需修正後重驗。本庫未附重跑資料與程式；原提案抽樣 MAE 約 7.12 格是另一實驗，不作前後改善比較。H2／H3 與抵達推薦效益尚未驗證。預期貢獻是可追溯、可棄權且可被實驗否證的抵達決策流程；臺中資訊型原型及 Birmingham 路外資料不等同新北服務已完成。[原始設計 §10–15](../../DESIGN.md) [城市與階段界線](../refactor/SOURCE_SCOPE_RECONCILIATION.md)

## Exact A–F map

| Code | Source-supported argument | Research state |
| --- | --- | --- |
| A — Attention Getter | SFpark reported search time 11:36 → 6:36 (−43%); query-time vacancy may disappear before arrival | External motivation, not New Taipei or Agent effect |
| B — But/Gap | Demand, delay, source quality, uncertainty | Problem framing |
| C — Cure | Agent automatically collects, validates, analyzes and recommends with evidence or abstains | Planned New Taipei workflow |
| D — Development | Three groups: context/data acquisition; temporal prediction/risk analysis; decision/autonomous orchestration | Proposed New Taipei integration; tools and workflow in AGENT_WORKFLOW.md |
| E — Experiments | Chronological/purged split; H1/H2/H3 comparisons | Some source-reported Phase 2 offline, no verified H2/H3 |
| F — Findings & boundaries | 7.12 early sample; source-reported Phase 2 Persistence best; real recommendation outcome unknown | Source-reported, not reproduced here |

**Important:** The two MAEs come from **different source-described experiments** and must not be compared as if they used a matched test set. The 0.3268 value is a regression MAE in parking spaces, **not** a parking-success probability. SFpark percentages are excluded from Findings because they are external policy outcomes.

The Chinese abstract follows the approximate short-summary length used in class; final submission length is subject to course instructions.
