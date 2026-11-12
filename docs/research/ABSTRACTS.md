# Refactored A–F Abstracts — New Taipei Proposal

> Newly authored academic proposal summaries derived from the original DOCX, the later DESIGN.md and the paper audit. **Not** a claim that the LMS already received this revised text. Keep historical sample and Phase 2 results separate.

## 中文摘要（約 300 字；A–F 對應）

路邊停車資訊顯示「目前有位」，不代表駕駛抵達時仍有空位（A）。需求變動、觀測延遲、來源故障與預測誤差，可能使即時查詢產生錯誤引導（B）。本研究以新北市路邊路段為對象，提出具資料品質閘門、抵達時間風險判斷與可追溯 Top-k 建議的智慧停車 AI Agent；證據不足時退回基準或棄權（C）。方法整合歷史 JSONL、預定即時 API、時間特徵、Persistence／樹模型、Retry／Replan 及證據紀錄（D）。研究規劃依時間切分並排除跨界標籤洩漏，比較 MAE、滿位校準、Top-3 成功率與異常推薦品質（E）。原提案報告抽樣 MAE 約 7.12 格；後續設計文件記載新北離線測試以 Persistence 的 MAE 0.3268 最佳，但實驗程式未隨本儲存庫提供。正式推薦及 Agent 效益仍待驗證（F）。

## IEEE-style English abstract (proposal, not completed results)

**Title—**An Uncertainty-Aware AI Agent for Arrival-Time Parking Availability Prediction and Risk-Aware Recommendation

**Abstract—**A parking space reported as vacant at query time may no longer be available when a driver arrives. Dynamic roadside occupancy, delayed observations, and source failures complicate reliable guidance. This study proposes an evidence-aware smart parking AI agent for roadside segments in New Taipei City, Taiwan, combining source-quality validation, arrival-horizon-aligned forecasting, candidate-specific risk assessment, and traceable Top-k recommendations. The proposed workflow includes baseline and tree-based models, bounded retry and replanning, fallback, and abstention when trustworthy evidence is unavailable. A chronological 60/20/20 evaluation with purged cross-boundary targets is planned; prediction error, fullness-risk calibration, arrival-time Top-3 success, selective coverage, and fault-injection outcomes will be compared against matched baselines and a fixed pipeline. The original proposal reports an early sample-notebook MAE of approximately 7.12 spaces. A later design document reports New Taipei offline MAEs of 0.3268 for persistence, 0.4027 for random forest, and 0.5375 for histogram gradient boosting, with persistence performing best overall. These experiments are not reproducible from the current repository, and the offline evaluation does not establish a deployable New Taipei prediction service or successful arrival-time recommendations. The intended contribution is a falsifiable integration of data provenance, decision-time risk awareness, and failure-aware agent orchestration rather than a claim of proven superiority.

**Index Terms—**Smart parking, arrival-time prediction, AI agent, data quality, uncertainty-aware recommendation, intelligent transportation systems.

## Exact A–F map

| Code | Source-supported argument | Research state |
| --- | --- | --- |
| A — Attention Getter | Query-time vacancy does not guarantee arrival-time vacancy | Motivation |
| B — But/Gap | Demand, delay, source quality, uncertainty | Problem framing |
| C — Cure | Quality-aware risk policy and Top-k with abstention | Planned New Taipei workflow |
| D — Development | JSONL / proposed API / baselines / Agent controls | Proposed New Taipei integration |
| E — Experiments | Chronological/purged split; H1/H2/H3 comparisons | Some source-reported Phase 2 offline, no verified H2/H3 |
| F — Findings & boundaries | 7.12 early sample; source-reported Phase 2 Persistence best; real recommendation outcome unknown | Source-reported, not reproduced here |

**Important:** The two MAEs come from **different source-described experiments** and must not be compared as if they used a matched test set. The 0.3268 value is a regression MAE in parking spaces, **not** a parking-success probability. SFpark percentages are excluded from Findings because they are external policy outcomes.

The formal word/character requirement is not independently verified from LMS; target ~300 Chinese characters is based on class demonstration, not an enforced journal limit.