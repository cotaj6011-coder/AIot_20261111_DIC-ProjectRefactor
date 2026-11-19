# 2026-11-18 課堂回饋與 DIC3 修訂對照

**依據：**2026-11-18 課堂逐字稿（本機來源），時間索引如下。本表核對老師對 DIC3 的共通批改；未找到針對本智慧停車專題的個別評語。逐字稿有辨識誤差，以作業頁要求及可查證來源為準。

| 時間 | 老師建議／關鍵原文 | 此次修訂檔案 | 驗證方式 |
| --- | --- | --- | --- |
| 00:13:04–00:13:47；01:36:21–01:36:24 | A 的證據須直接支持研究必要性：「資料要直接相關」，不能只放宏觀市場數字。 | [ABSTRACTS.md](../research/ABSTRACTS.md)、[INTRODUCTION.md](../research/INTRODUCTION.md)、[REFERENCE_AUDIT.md](../references/REFERENCE_AUDIT.md) | 逐項核對數字的原始來源、研究場域與適用範圍；不將國外政策成效當作本 Agent 的成果。 |
| 01:03:20–01:04:31；01:16:33–01:17:48 | A–F 要「一個扣一個」；前文未證明原因時，不可直接寫「顯示」特定因果。 | [ABSTRACTS.md](../research/ABSTRACTS.md)、[INTRODUCTION.md](../research/INTRODUCTION.md)、[RELATED_WORK.md](../research/RELATED_WORK.md) | 檢查證據→現有限制→研究問題→解法→評估的銜接；區分已觀察現象、推論與待驗證假設。 |
| 00:59:28–01:01:24；01:14:14–01:15:13 | 中文 300 字及英文摘要必須保留關鍵數字、痛點與方法：「我們是壓縮……不是丟掉」。 | [ABSTRACTS.md](../research/ABSTRACTS.md) | 對照 A–F 詳述、中文短摘要及英文摘要，確認關鍵數字與研究界線一致，並檢查字數。 |
| 01:10:20–01:10:54；01:12:16–01:13:18 | 方法先分類，再寫實際演算法／工具名稱，避免只有 GIS Engine、Recommendation Engine 等泛稱。 | [INTRODUCTION.md](../research/INTRODUCTION.md)、[RESEARCH_5_3_10.md](../research/RESEARCH_5_3_10.md)、[AGENT_WORKFLOW.md](../research/AGENT_WORKFLOW.md) | 檢查方法分組、模型／基準名稱、責任與適用條件；規劃中的方法不得寫成已部署。 |
| 01:06:55–01:07:18 | 「目標是要寫 agent，不是寫 app 而已」；須能自主收集、分析與行動。 | [AGENT_WORKFLOW.md](../research/AGENT_WORKFLOW.md)、[INTRODUCTION.md](../research/INTRODUCTION.md) | 流程須包含資料取得、品質判斷、Retry／Replan／Abstain；以同條件固定 Pipeline 對照設計檢驗 H3，不以聊天介面宣稱成效。 |
| 00:20:51–00:21:08 | 架構圖之外，補上「先做這個，再做這個」的 Workflow。 | [AGENT_WORKFLOW.md](../research/AGENT_WORKFLOW.md) | 已核對文件包含逐步流程、失敗分支、輸入輸出與抵達後核對；這是設計文件，並非系統已實作的證明。 |
| 00:09:48–00:10:35；00:54:46–00:54:58 | 一頁資訊圖表要看出核心賣點、A–F、方法與亮點，並與研究論述一致。 | [修訂資訊圖表](../assets/smart-parking-infographic-v2.png)、[README.md](../../README.md) | 已目視校對 A–F、時間、43%、MAE 單位／數值及研究狀態；修正 D／E 標記及重試分支。PNG 原尺寸 1491×1055，可點開閱讀；本機 README 圖片已置頂。 |
| 00:50:00–00:50:38；00:51:38–00:51:42 | GitHub 不要藏在後面；內容盡量直接呈現，讓老師「一次就看到」。 | [README.md](../../README.md)、iLearning DIC3 作業內容 | iLearning 草稿已儲存並實際確認圖表置頂、可開啟原圖、GitHub 入口位於圖下。線上 GitHub 同步與正式繳交狀態另依最終紀錄。 |

## 本次作業範圍與驗證界線

- 02:28:38–02:28:48 明確說「Doing Class 我有重開喔」；應回到本次作業頁修訂，截止日依平台公告，不自行推定新期限。
- 02:27:32–02:27:38 表示 OpenSpec 尚未完整講授；本次沿用 DIC3 既有 OpenSpec 要求，並非宣稱老師於本堂新增固定檔案格式。
- OpenSpec CLI 已有實際 **PASS** 紀錄，見 [OPENSPEC_CLI_VERIFICATION.md](OPENSPEC_CLI_VERIFICATION.md) 及 [原始 JSON](OPENSPEC_CLI_VALIDATION.json)。CLI 格式驗證不等於模型實驗通過、資訊圖表驗收或 iLearning 已提交。
- 五頁論文、完整系統與實驗、12/26 收件及成果影片屬期末脈絡；實際投稿在 00:29:18–00:29:24 改稱 Optional，不擴增為本次 DIC3 必交成果。
- 01:37:39–01:38:54 的 48% 違規停車數字是另一個 UAV 執法研究的例子，不能直接移植為本停車推薦專題的證據。

詳細修訂前後對照見 [BEFORE_AFTER.md](BEFORE_AFTER.md)。
