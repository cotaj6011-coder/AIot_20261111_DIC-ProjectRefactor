# A–F Aligned Abstracts (Proposal Status)

> These are **newly refactored proposal abstracts**, not replacements claimed to be identical to the LMS submission. The A–F labels describe argument structure; IEEE-style final abstract below is one coherent paragraph. Results are not invented.

## 中文濃縮摘要（約 300 字，A–F）

駕駛查詢停車資訊時顯示「目前有位」，不代表抵達時仍可停車（A）。路邊停車需求變化、資料延遲、來源失效及預測不確定性，可能讓即時資訊無法支持可靠決策（B）。本研究以新北市路邊停車路段為對象，提出具資料品質閘門與風險感知的智慧停車 AI Agent，依預計抵達時間提供可追溯的 Top-k 建議，並在證據不足時退回基準或棄權（C）。系統規劃整合歷史 JSONL、即時 API、時間與路段特徵、Persistence 與樹模型，以及 Retry／Replan 與證據紀錄（D）。評估將採防洩漏的時間切分，比較 MAE、RMSE、滿位機率校準、Top-3 成功率與異常情境下的無證據推薦率（E）。現有提案記載抽樣 MAE 約 7.12 格，但尚無可於本儲存庫重現的完整實驗；全量資料品質、H1–H3 與實際推薦效益仍待驗證（F）。

## English IEEE Transactions-style proposal abstract

**Title—An Uncertainty-Aware AI Agent for Arrival-Time Parking Availability Prediction and Risk-Aware Recommendation**

**Abstract—**Real-time parking availability does not guarantee that a space will remain available when a driver arrives. In roadside settings, demand variation, observation latency, incomplete records, and source failures further undermine the reliability of static recommendations. This study proposes an evidence-aware smart parking AI agent for roadside segments in New Taipei City, Taiwan. The proposed architecture combines historical JSON Lines observations, a planned real-time data connector, schema and freshness validation, horizon-aligned persistence and tree-based prediction, candidate-specific risk rules, and traceable Top-k recommendations. Retry, replanning, fallback, and abstention are specified for cases in which reliable observations or sufficiently supported predictions are unavailable. A chronological 60/20/20 evaluation with safeguards against overlapping time-window leakage is planned. Persistence and historical-median baselines will be compared with candidate models using mean absolute error and root mean squared error; occupancy-risk calibration, arrival-time Top-3 success, selective coverage, and evidence-less recommendation rates will also be evaluated. An earlier sample notebook is reported in the source proposal to yield an MAE of approximately 7.12 spaces, but its underlying experiment is unavailable in this repository and does not establish operational feasibility or model superiority. The intended contribution is an experimentally testable integration of arrival-time prediction, source-quality awareness, and failure-aware decision support; its effectiveness remains to be demonstrated.

**Index Terms—**Smart parking, artificial intelligence agents, arrival-time prediction, data quality, uncertainty-aware recommendation, intelligent transportation systems.

## A–F mapping

| Component | Chinese | English |
| --- | --- | --- |
| A | 現在有位不等於抵達有位 | Opening sentence |
| B | 需求變化、來源失效、資料延遲 | Motivation and limitations |
| C | Agent 與 Top-k 風險感知推薦 | Proposed architecture and policy |
| D | JSONL/API/模型/Retry | Architecture details |
| E | 時間切分、Baseline、MAE、Top-3 | Proposed evaluation protocol |
| F | 抽樣 7.12 但待重現，全量未完成 | Exploratory source claim and explicit limitations |

**Publication note:** Unlike a completed experimental paper, the English abstract uses prospective language. SFpark results are intentionally moved to the Introduction's external motivation, not presented as this study's findings.
