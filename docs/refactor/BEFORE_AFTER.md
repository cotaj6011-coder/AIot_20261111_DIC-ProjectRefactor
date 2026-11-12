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
