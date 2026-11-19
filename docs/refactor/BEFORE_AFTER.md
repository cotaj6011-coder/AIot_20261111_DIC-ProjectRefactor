# Before / After — 研究提案重構對照

**原稿來源：**[DOCX](../submission/智慧停車AI_Agent_Proposal_新北市%281%29.docx)、[PPTX](../submission/智慧停車AI_Agent_Proposal_新北市%281%29.pptx)、[DESIGN.md](../../DESIGN.md)、[提案解析 PDF](../submission/智慧停車提案解析.pdf)；另保留 [README 原稿快照](../baseline/README_BEFORE.md)。

| 原始段落／內容 | 重構文件 | 核心改善 |
| --- | --- | --- |
| DOCX Abstract A–F | [ABSTRACTS.md](../research/ABSTRACTS.md) | 以 A–F 建立一致論述；區分抽樣與 Phase 2 離線數據，不虛構實驗成果 |
| DOCX §1.1–1.3 背景、問題、研究缺口 | [INTRODUCTION.md](../research/INTRODUCTION.md) §§A–C | 明確定義查詢時間 `t`、抵達時距 `h`、資料品質、可驗證研究缺口 |
| DOCX §1.4–1.6 H1–H3、Agent 必要性、貢獻 | [INTRODUCTION.md](../research/INTRODUCTION.md) §§D–F | 定義可反駁假設、Baseline、固定 Pipeline 對照與貢獻範圍 |
| DOCX §2.1–2.2 Related Work | [RELATED_WORK.md](../research/RELATED_WORK.md) | 原稿九項文獻 [5]–[13] 分類比較，指出可移植性限制 |
| DOCX §3.1–3.3 Five／Three／Ten | [RESEARCH_5_3_10.md](../research/RESEARCH_5_3_10.md) | 每項問題對應證據、實驗或決策條件 |
| DOCX §4 Agent 流程及偽程式碼、PPTX 9–11 頁 | [INTRODUCTION.md](../research/INTRODUCTION.md) §E | 明確區分規劃流程與可實證的 Agent 增益 |
| DOCX §5–7、PPTX 12–16 頁 | [INTRODUCTION.md](../research/INTRODUCTION.md) §§D–F | 補上可重現的研究設計、實驗狀態與判定界線 |
| DESIGN.md §§10–11 新北離線比較／品質限制 | [SOURCE_SCOPE_RECONCILIATION.md](SOURCE_SCOPE_RECONCILIATION.md) · [INTRODUCTION.md](../research/INTRODUCTION.md) | 說明 Persistence 整體較佳與未修正的切分邊界問題 |
| DESIGN.md §§12–15 臺中 Agent | [SOURCE_SCOPE_RECONCILIATION.md](SOURCE_SCOPE_RECONCILIATION.md) | 區分臺中已記載的資訊型功能與新北預測研究 |
| 原稿參考文獻 [5]–[13] | [REFERENCE_AUDIT.md](../references/REFERENCE_AUDIT.md) | 核對九項研究的書目、方法與限制 |

## 保留的重要研究界線

- 抽樣 MAE 約 7.12 與 Phase 2 MAE 0.326757 的實驗樣本及設計不同，不能直接比較。
- 原設計記載的 Phase 2 整體 MAE 不支持 RF／HistGB 優於 Persistence。
- 文獻存在不代表研究結果已移轉至新北市；SFpark 的城市政策成效不是本 Agent 的成效。
- 文件中的設計與測試計畫不等於模型已部署或 H2／H3 已驗證。

**對照結果：**已完成原稿與重構文件的章節級內容對照。原始 DOCX／PPTX／PDF／DESIGN.md 未修改。

## 2026-11-18 課堂回饋修訂

本輪依 [課堂回饋核對表](CLASS_FEEDBACK_20261118.md) 修訂，保留上方原稿對照；完整期末實作及成果不納入本次 DIC3 完成宣稱。

| 修訂前需改善之處 | 此次修訂內容與檔案 | 驗證方式／狀態 |
| --- | --- | --- |
| A–F 有資料，但仍須檢查痛點證據的直接相關性與各段邏輯。 | [ABSTRACTS.md](../research/ABSTRACTS.md)、[INTRODUCTION.md](../research/INTRODUCTION.md)、[RELATED_WORK.md](../research/RELATED_WORK.md) 對齊證據、限制、解法與評估；[REFERENCE_AUDIT.md](../references/REFERENCE_AUDIT.md) 核對來源。 | 核對數字、來源與推論範圍，不把國外研究或政策結果寫成本專題成效。 |
| 摘要濃縮可能丟失關鍵數字，或與 A–F 詳述脫節。 | [ABSTRACTS.md](../research/ABSTRACTS.md) 同步整理 A–F、中文短摘要與英文摘要。 | 對照數字、痛點、方法及研究狀態，檢查短摘要字數。 |
| 方法與 Agent 行為需要具體化，架構敘述不足以呈現執行順序。 | [RESEARCH_5_3_10.md](../research/RESEARCH_5_3_10.md)、[INTRODUCTION.md](../research/INTRODUCTION.md) 與新增 [AGENT_WORKFLOW.md](../research/AGENT_WORKFLOW.md) 對齊三組方法、具體模型／基準、逐步流程及失敗分支。 | Workflow 已包含輸入輸出、品質判斷、Retry／Replan／Abstain、抵達核對與固定 Pipeline 對照設計；不宣稱 H2／H3 已完成實驗。 |
| OpenSpec 僅有人工規格檢查，缺少 CLI 執行證據。 | 新增 [OPENSPEC_CLI_VERIFICATION.md](OPENSPEC_CLI_VERIFICATION.md) 與 [OPENSPEC_CLI_VALIDATION.json](OPENSPEC_CLI_VALIDATION.json)。 | 已實際 PASS，exit code 0、0 issues；僅證明 OpenSpec 格式通過。 |
| 資訊圖表須反映本輪內容，且入口需讓老師立即看見。 | 已更新 [修訂資訊圖表](../assets/smart-parking-infographic-v2.png)，置於本機 [README.md](../../README.md) 與 iLearning DIC3 作業內容最前面。 | 已目視校對文案、數值、字樣與流程分支；iLearning 草稿已儲存且圖片載入正常。線上 GitHub 同步與正式繳交依最終紀錄。 |

