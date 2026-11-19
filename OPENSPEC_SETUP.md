# OpenSpec 使用說明

本儲存庫已提供：

- `openspec/config.yaml`：研究文件的規格與來源原則。
- `openspec/changes/refactor-smart-parking-proposal/`：Proposal／Specs／Design／Tasks。
- `.agents/skills/` 及 `.github/skills/`：供支援的 Agent 工具使用的 OpenSpec Skills。
- [人工規格驗收](docs/refactor/OPENSPEC_MANUAL_VERIFICATION.md)：逐項 Requirement／Scenario 文件證據。

## 本次安裝與驗證

2026-11-19 已在本專案 `.tools/openspec-2.1.0/` 安裝官方 **Windows x64 standalone OpenSpec 2.1.0**，並核對官方 `SHA256SUMS`。此安裝不需要 npm，也未修改系統 PATH；工具執行檔僅供本機使用，不屬繳交附件。官方安裝方式見 [Installation](https://openspec.dev/docs/installation)，固定版本見 [v2.1.0 release](https://github.com/Fission-AI/OpenSpec/releases/tag/v2.1.0)。

在專案根目錄實際執行：

```powershell
& '.\.tools\openspec-2.1.0\openspec.exe' --version
& '.\.tools\openspec-2.1.0\openspec.exe' list
& '.\.tools\openspec-2.1.0\openspec.exe' status --change refactor-smart-parking-proposal --json
& '.\.tools\openspec-2.1.0\openspec.exe' validate refactor-smart-parking-proposal --strict --no-interactive --json
```

**結果：原生 CLI 嚴格驗證 PASS，1 項 change 通過、0 項失敗、0 個 issue，exit code 0。** 四個規劃文件（proposal、specs、design、tasks）皆可由 CLI 辨識。詳見 [執行紀錄](docs/refactor/OPENSPEC_CLI_VERIFICATION.md) 與 [原始 JSON](docs/refactor/OPENSPEC_CLI_VALIDATION.json)。

CLI PASS 檢查的是 OpenSpec 文件結構與規格格式；人工文件驗收另列，兩者均不代表 H1–H3 實驗完成或 iLearning 已繳交。

