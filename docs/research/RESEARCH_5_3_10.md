# DIC3 Deep Research — A–F, 5 Mindsets, 3 Controversies, 10 Questions

**Source baseline:** Original [11-page proposal DOCX](../submission/智慧停車AI_Agent_Proposal_新北市%281%29.docx) §3.1–3.3. All source categories retain the original instructor-facing structure. Updated with later-design facts and testable decisions; not a claim that the original assignment PDF was itself rewritten.

## A–F argument structure

| A–F | Research statement | Status |
| --- | --- | --- |
| **A — Attention Getter** | A free parking space at query time may be occupied upon arrival | Motivation |
| **B — But / Gap** | Demand changes, delayed observations and source errors make simple current-state recommendations unreliable | Problem |
| **C — Cure** | Quality-gated, evidence-aware arrival-time Top-k risk recommendation with explicit abstention | Proposed New Taipei service |
| **D — Development** | New Taipei JSONL, proposed API, past-only features, Persistence/statistical/tree models, planner/Retry/Replan/HITL | Method design; separate Taichung information-only prototype described in DESIGN |
| **E — Experiments** | Matched/chronological/purged model tests, calibration, arrival Top-k utility and Agent-vs-fixed-pipeline faults | New Taipei Phase 2 offline test source-reported, H2/H3 pending |
| **F — Findings / limitations** | Early sample MAE ≈7.12; later offline Persistence 0.326757 vs RF 0.402669 / HistGB 0.537539 (source-reported); no production-ready model, purged test, H2/H3 | Distinct stages, neither rerun in repo |

## 1. Five Mindsets（五大思維）

1. **資料品質優先於模型複雜度。** 在建模前先評估 schema、路段鍵、時間戳、缺值、容量和來源品質；資料遺失不可直接補零。**驗證：**報告可用資料比例、有效路段數與異常率。
2. **預測必須對應抵達 Horizon。** 30/60 分鐘是不同目標；不得用 30 分鐘時段特徵冒充 10 分鐘預測結果。**驗證：**依 horizon 報告 matched baseline 與缺失 label 比例。
3. **保留空間與營運語意。** 路邊路段、路外場站、臺中 snapshot 與新北歷史資料不可視為相同觀測單位。**驗證：**分源 schema、路段 ID 與容量一致性。
4. **先用強 Baseline，接受模型不勝出的結果。** DESIGN.md 所述 Phase 2 persistence 已在整體 MAE 最佳。**驗證：**同一 test row/horizon 的 RF、HistGB、Persistence、Historical Median 排序及變動子集分析。
5. **不確定性要成為決策條件。** source freshness、校準、coverage、risk 和 abstention 須一起衡量。**驗證：**selective risk/coverage 曲線及無證據推薦率。

## 2. Three Controversies（三大爭議）

1. **簡單模型 vs. 深度時空模型。** 複雜模型能否抓住路段變動，必須與資料品質、推論成本、horizon 與時序洩漏控制一同檢驗；來源報告的整體結果反而支持 Persistence，不能預設深度方法更優。
2. **跨路段共用模型 vs. 路段專屬模型。** 共用模型資料多但可能模糊在地差異，個別模型易受稀疏資料影響；比較 shared + segment features、regional、per-segment 的分層效果。
3. **低 MAE 點預測 vs. 可校準風險推薦。** 低 MAE 不保證抵達成功；以正確的滿位標籤、校準、走路距離及棄權覆蓋率評估使用者實際效益。

## 3. Ten Deep Questions（十大深問）

| # | Prompt category | Testable question and evidence |
| --- | --- | --- |
| 1 | **Why** | 為何抵達時間比查詢時更重要？依路段與 horizon 統計 t→t+h 變動及滿位轉換。 |
| 2 | **Evidence** | 新北 JSONL 的時間涵蓋、路段數、更新節奏與合法配對 label 有多少？產出全量 QA。 |
| 3 | **What-if** | API timeout、stale 或 schema 變動時，Agent 何時 retry/replan/fallback/abstain？用故障注入驗證。 |
| 4 | **Trade-off** | 較近但高滿位風險與較遠且較穩定的路段如何取捨？畫出距離/風險 Pareto 關係。 |
| 5 | **Failure case** | 錯誤狀態碼、缺容量、重複主鍵如何破壞聚合？量測 quality gate 排除率。 |
| 6 | **Comparison** | Agent 相對固定 Pipeline 是否改善有證據的建議率？維持相同輸入和工具比較。 |
| 7 | **Leakage** | Phase 2 標籤跨名義切分邊界應如何 purge？核對 target_time ≤ split_end，並重做測試。 |
| 8 | **Transfer** | Birmingham 與臺中有哪些 QA/工具方法可移植？哪些模型效能不可推論至新北？ |
| 9 | **Ground truth** | 抵達後第一筆合法觀測容許窗怎麼訂？缺資料是否正確標示 Unknown 而非失敗？ |
| 10 | **Decision** | 在什麼校準、Top-3、coverage 與延遲條件下推薦、退回 Baseline 或棄權？事前訂門檻。 |

## Integrity statement

**Five** mindsets, **three** controversies, **ten** questions. The research is **not yet** a demonstrated New Taipei production service. DESIGN.md §§10–11 gives source-reported offline metrics and conditional trust; §§12–15 documents Taichung current-information Agent whose future prediction is disabled. Evidence state and per-city coverage are documented in [SOURCE_SCOPE_RECONCILIATION](../refactor/SOURCE_SCOPE_RECONCILIATION.md).
