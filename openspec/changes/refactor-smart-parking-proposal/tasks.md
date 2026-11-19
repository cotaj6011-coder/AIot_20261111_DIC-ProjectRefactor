# Tasks — Smart Parking Proposal Refactor

## 原始資料與研究架構
- [x] 保存原始 DOCX、PPTX、PDF、DESIGN.md 及重構前 README 快照。
- [x] 建立原稿與 Introduction／Related Work 的章節對照。
- [x] 區分新北離線預測、臺中資訊型 Agent 與 Birmingham 參考資料。

## OpenSpec 規格驅動流程
- [x] Proposal：明確定義問題、變更、能力及影響。
- [x] Specs：建立 9 項 Requirement 與相應 Scenario。
- [x] Design：訂定來源、風險、方法與驗收策略。
- [x] Apply：產生 A–F、5/3/10、Introduction、Related Work、文獻對照及 Before/After。
- [x] Verify：建立逐項人工驗證及驗收報告。
- [x] 安裝官方 OpenSpec 2.1.0；原生 `openspec validate refactor-smart-parking-proposal --strict --no-interactive --json` **PASS**（1 passed、0 failed、0 issues）；詳見 [CLI 紀錄](../../../docs/refactor/OPENSPEC_CLI_VERIFICATION.md)。

## 研究與學術品質
- [x] 對照原始提案的五大思維、三項爭議與十大深問。
- [x] 整理原始文獻 [5]–[13] 九項書目及研究範圍。
- [x] 區分原提案 7.12 MAE 與新北 Phase 2 的 0.326757／0.402669／0.537539 MAE。
- [x] 在章節中明確記載 Persistence 為原設計所報告的整體最佳 Baseline。
- [x] 明確區分 Implemented／Evaluated（來源記載）、Planned／Blocked 與本 Repo 已驗證文件。
- [ ] 以可重現資料執行 purged chronological split 並重新評估 H1（本 Repo 尚缺資料／執行證據）。
- [ ] 執行 H2 Top-3、校準與 H3 Agent-vs-Pipeline 正式對照。
- [x] 確認課程平台的實際上傳與評分要求：iLearning DIC3 頁列明五項作業、資訊圖表及摘要要求；截止 2026-11-20、比重 5%、不允許遲交（2026-11-19 實際頁面查核）。

## 文件驗收

- [x] 九項 Requirement／Scenario 具對應文件與證據。
- [x] A–F、5／3／10、Introduction、Related Work 與來源對照齊備。
- [x] 以連結與靜態結構檢查核對文件一致性。
- [x] 驗收與研究限制記錄於 [ACCEPTANCE.md](../../../docs/refactor/ACCEPTANCE.md) 及 [OPENSPEC_MANUAL_VERIFICATION.md](../../../docs/refactor/OPENSPEC_MANUAL_VERIFICATION.md)。

**完成範圍：文件規格、人工驗收與原生 CLI 嚴格驗證。** 研究實驗與課程平台提交需各自具備證據，不包含於 CLI PASS。

