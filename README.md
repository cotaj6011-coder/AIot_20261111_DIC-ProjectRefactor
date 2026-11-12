# 智慧停車 AI Agent — DIC3 OpenSpec 提案重構

**研究主題：**新北市路邊停車抵達時間可用性預測與風險感知推薦  
**課程：**物聯網應用與資料分析｜DIC3 Project Proposal Refactor using OpenSpec  
**狀態：**研究提案文件已依 OpenSpec 規格進行來源對照與學術重構；**OpenSpec CLI 未執行、GitHub 內無可重現的完整預測實驗**。

> **必讀的範圍區分：**原始 DOCX 聚焦**新北市路邊抵達時間預測**；後續 `DESIGN.md` 記錄**新北離線 Phase 2/2.5** 與另一個**臺中資訊型 Agent**。臺中 Agent 的未來預測為 **DISABLED**，不能稱為已完成新北抵達時間推薦部署。

## 1. 老師驗收導覽

| 要求或證據 | GitHub 檔案 | 內容狀態 |
| --- | --- | --- |
| OpenSpec Proposal | [proposal.md](openspec/changes/refactor-smart-parking-proposal/proposal.md) | **PASS 文件** |
| OpenSpec Delta Specs | [spec.md](openspec/changes/refactor-smart-parking-proposal/specs/research-proposal-refactor/spec.md) | **PASS 文件語法人工檢查** |
| OpenSpec Design | [design.md](openspec/changes/refactor-smart-parking-proposal/design.md) | **PASS 文件** |
| OpenSpec Tasks | [tasks.md](openspec/changes/refactor-smart-parking-proposal/tasks.md) | **PASS 追蹤，保留未完成項** |
| A–F 與 5/3/10 | [RESEARCH_5_3_10.md](docs/research/RESEARCH_5_3_10.md) | **PASS** |
| 約 300 字中文與 IEEE 英文摘要 | [ABSTRACTS.md](docs/research/ABSTRACTS.md) | **PASS 文件** |
| 重構 Introduction | [INTRODUCTION.md](docs/research/INTRODUCTION.md) | **PASS 文件** |
| 重構 Related Work（原稿九篇） | [RELATED_WORK.md](docs/research/RELATED_WORK.md) | **PASS 九篇比較** |
| 參考文獻 DOI 與主張稽核 | [REFERENCE_AUDIT.md](docs/references/REFERENCE_AUDIT.md) | **9/9 出版資訊／摘要核對** |
| 原稿／重構對照 | [BEFORE_AFTER.md](docs/refactor/BEFORE_AFTER.md) | **PASS 章節層級對照** |
| 臺中／新北階段與證據歸屬 | [SOURCE_SCOPE_RECONCILIATION.md](docs/refactor/SOURCE_SCOPE_RECONCILIATION.md) | **PASS** |
| 完整驗收報告 | [ACCEPTANCE.md](docs/refactor/ACCEPTANCE.md) | **文件 PASS；實驗／CLI NOT RUN** |

## 2. 完整保留的原始文件

| 原始來源 | 位置 | 說明 |
| --- | --- | --- |
| **原始新北市提案 DOCX** | [智慧停車AI_Agent_Proposal_新北市(1).docx](docs/submission/智慧停車AI_Agent_Proposal_新北市%281%29.docx) | 原稿含 A–F、Introduction、Related Work [5]–[13]、5/3/10、Agent、Evaluation |
| **原始新北市提案 PPTX** | [智慧停車AI_Agent_Proposal_新北市(1).pptx](docs/submission/智慧停車AI_Agent_Proposal_新北市%281%29.pptx) | 16 張原始簡報：動機、H1–H3、Related Work、5/3/10、架構、流程、評估、原型與狀態；保留原稿，不視為更新後實驗報告 |
| **原始 DESIGN.md** | [DESIGN.md](DESIGN.md) | 記錄跨城市設計與後續離線／資訊 Agent 進度 |
| **原始提案解析 PDF** | [智慧停車提案解析.pdf](docs/submission/智慧停車提案解析.pdf) | 四頁原始分析，內容不隨重構自動更新 |
| **OpenSpec 前 README 快照** | [README_BEFORE.md](docs/baseline/README_BEFORE.md) | 保留早期提交版本，供比對 |

本次**不修改**以上原始來源；DOCX、PPTX 都是原始提案階段材料，內容若與後續 `DESIGN.md` 記錄的 Phase 2/2.5 進度不同，應以文件版本與時間區分，而非直接視為同一階段的結論。課堂系統已交的圖檔不必假定也須重複存入 GitHub；iLearning 正式規格未在本 Repo 獨立核驗。

## 3. 研究內容摘要與已知限制

本研究欲回答：駕駛查詢路邊停車時，即便目前顯示有空位，**抵達時是否仍可用、風險多高、哪個 Top-k 路段值得優先前往？** 預計整合歷史 JSONL、資料品質閘門、時間對齊預測、風險排序、Agent tool selection、Retry/Replan、證據紀錄以及證據不足時的 Abstain。

### 不能混為一談的兩個既有數值

| 階段與來源 | 報告結果 | 可下的結論 |
| --- | --- | --- |
| **原始提案 DOCX 抽樣 Notebook** | MAE 約 **7.12 格** | 早期來源聲明，樣本／切分與模型細節未在此 Repo 重現 |
| **DESIGN.md 新北 Phase 2 離線評估** | 相同 9,178,935 test rows：Persistence **0.326757**、RF **0.402669**、HistGB **0.537539** MAE | 原設計記錄的整體離線比較以 Persistence 最佳；**此 Repo 未重跑，且不代表新北預測系統可部署** |

後續 DESIGN §11 明列**名義切分邊界的 future labels 越界**、多數觀測不變與評估覆蓋條件等限制。因此後續要採 **purged chronological split** 修正，再依 H1–H3 重做可重現比較。

### H1–H3 狀態

- **H1（樹模型勝過 Persistence）：**DESIGN.md 所記載的整體離線比較**不支持**優越假設；尚待可重現、修正邊界的正式實驗。
- **H2（風險感知 Top-3）：**沒有可在本 Repo 驗證的抵達成功率和校準結果，**Planned / NOT RUN**。
- **H3（Agent 比固定 Pipeline 更可靠）：**沒有匹配工具與故障注入的實測比較，**Planned / NOT RUN**。

## 4. OpenSpec 進度與執行方式

GitHub 上含 OpenSpec 設定、Codex／Copilot Skills 及本次 `refactor-smart-parking-proposal` 的 Proposal／Delta Spec／Design／Tasks。此工作由 **ChatGPT GitHub Connector 直接提交 Markdown**，不是在遠端主機安裝 CLI。

- 文件存在、相互連結、原始章節對應與 delta-spec 語法可由 GitHub 人工驗收。
- **尚未執行** `openspec init`、`openspec validate` 或原始專案的 Python 測試及模型訓練。
- 本 Repo 中的 DESIGN.md 引用的 `src/`、`web/`、`PHASE2_REPORT.md` 等來源工作區檔案**未包含在這個文件交付 Repo**，不能用路徑文字當成已驗收的程式。

如需本機原生 OpenSpec，另見 [OPENSPEC_SETUP.md](OPENSPEC_SETUP.md)。**文件規格完成 ≠ OpenSpec CLI 驗證成功 ≠ 新北模型驗證成功。**

## 5. 可追溯性與建議後續

1. [查看原始對修訂章節](docs/refactor/BEFORE_AFTER.md)，含 DOCX §1–§3 與 DESIGN §§9–15 的依據。
2. [查看完整文獻核對](docs/references/REFERENCE_AUDIT.md)，原稿九篇 [5]–[13] 均有外部來源資訊，但不是全部實驗結果的獨立重現。
3. [查看驗收報告](docs/refactor/ACCEPTANCE.md)，保留 PASS/PARTIAL/BLOCKED/NOT RUN 與可行的後續工作。

**原則：Evidence first · Abstain when uncertain · Do not claim a result without the matching experiment.**
