# 資訊圖表生成規格

工具：內建 imagegen；原圖僅作風格參考。最終檔案：`smart-parking-infographic-v2.png`。

校稿修訂：補齊 A–F 的 D／E 標記；重試返回資料取得、棄權獨立分支；MAE 表頭補上單位「格」。逐字核對兩組時間、43%、三項 MAE 與研究狀態。A4 橫式比例 PNG，實際尺寸以檔案為準。

Use case: infographic-diagram.
Create one polished, high-resolution A4 landscape academic infographic in Traditional Chinese for a Taiwan university DIC3 research-proposal assignment. Referenced image is ONLY a STYLE REFERENCE. Preserve its dark navy background, luminous cyan rounded panel outlines, bold white Traditional Chinese typography, aqua numbered chapter badges, parking/car skyline line icons, white/light-blue data rows, and disciplined dense technical-blueprint feel. Entirely REPLACE its outdated content with the exact verified content below. Do NOT copy the obsolete self-grading checklist or claims of implemented New Taipei predictive service. Request 3072×2176 or higher landscape A4-ratio rendering. Typography MUST be impeccably legible, not tiny: large headings, generous line spacing, no overlapping text. Chinese text must be accurate and sharp. Prioritize a readable summary over decorative density.
Title: 智慧停車 AI Agent｜抵達時，真的有位嗎？
Subtitle: 新北市路邊停車・DIC3 OpenSpec 提案重構
Small status strip: 研究提案｜外部證據 ≠ 本專題成效｜來源記載 ≠ 本次重跑
Layout: upper row three clear panels 01/02/03, middle full-width panel 04 workflow, bottom row two wide panels 05/06. Clear left-to-right reading order.

01 痛點與直接證據
Large hero numbers: 11分36秒 → 6分36秒
Caption: SFpark 試辦區自陳尋位時間｜減少 43%
Body: 舊金山停車資訊與需求定價整體案例；非新北數據，非本專題成效。
Bold question: 現在有位 ≠ 抵達有位
Body: 決策目標：在步行限制內，找到抵達時可用的候選路段。

02 A–F 一條研究邏輯
Six easily readable rows:
A 注意｜尋位耗時，需要可靠引導
B 缺口｜即時餘位無法保證抵達可用
C 解法｜具資料證據的停車決策 Agent
D 方法｜品質檢查＋時間預測＋風險排序
E 評估｜時間切分、基準對照、故障注入
F 發現｜Persistence 暫優；推薦效益待驗證

03 三項設計亮點
1 情境感知：目的地、抵達時間、步行距離
2 證據決策：每個候選保留來源、時間、品質
3 自主調度：收集→分析→重試／重規劃→輸出
Small emphasized line: 新北預測型 Agent：規劃中
Small line: 臺中資訊型 Agent：來源記載；預測停用

04 Agent Workflow｜規劃流程
Big six-box horizontal arrow flow with simple icons, EXACT box text:
① 目的地與抵達時間
→ ② Planner 選工具、取 JSONL／API
→ ③ Schema／時效／容量檢查
→ ④ 僅用過去特徵，選模型或基準
→ ⑤ 風險與步行條件排序，附證據
→ ⑥ Top-3 建議與抵達核對
Below boxes show an explicit failure loop:
資料失敗 → 有界 Retry／Replan → 回到資料取得
And a separate terminal branch:
仍無足夠證據 → 棄權 Abstain
Below, three short methods in one clean strip:
預測：Persistence／Random Forest／HistGradientBoosting
校準：Isotonic／Platt scaling（待驗證）
排序：風險、距離與來源品質規則（待驗證）

05 評估與證據界線
Two columns within panel:
LEFT header: 規劃評估
• 時間 60／20／20；排除跨界目標標籤
• H1 預測誤差：MAE／RMSE
• H2 抵達決策：Top-3 Success／Coverage
• H3 故障處理：Agent vs 固定 Pipeline
RIGHT header: 來源記載的離線 MAE（格）
Table:
Persistence 0.3268
Random Forest 0.4027
HistGB 0.5375
Below table: 同組比較以 Persistence 最佳。
Below whole panel: 上述結果非本次重跑；須修正切分後重驗。H2／H3 尚未驗證。

06 5／3／10 深度思考
5 核心：資料品質・時間對齊・場景界線・基準比較・不確定性
3 取捨：簡單 vs 複雜模型／共用 vs 個別路段／誤差 vs 決策效益
10 追問：痛點、證據、故障、權衡、資料、Agent比較、洩漏、移轉、真值、門檻
Bottom highlighted takeaway: 核心價值：讓停車建議有依據、可驗證、可拒答。

Footer source line (readable, concise):
資料來源：SFMTA SFpark Evaluation（2014，印刷頁12–13）；本專題 DESIGN.md §10–11。完整引用與 A–F 見 README。
Footer final small line: DIC3｜2026-11-19｜新北市路邊研究提案

Do not add any data, claims, percentages, grading marks, checkmarks of completed experiments, QR codes or URLs not given above. No watermarks. All Chinese must be Traditional Chinese. Use large enough font for every body line and avoid superfluous tiny tags.
