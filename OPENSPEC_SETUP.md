# OpenSpec 使用說明

本儲存庫已提供：

- `openspec/config.yaml`：研究文件的規格與來源原則。
- `openspec/changes/refactor-smart-parking-proposal/`：Proposal／Specs／Design／Tasks。
- `.agents/skills/` 及 `.github/skills/`：供支援的 Agent 工具使用的 OpenSpec Skills。
- [人工規格驗收](docs/refactor/OPENSPEC_MANUAL_VERIFICATION.md)：逐項 Requirement／Scenario 文件證據。

## 驗證方式

**目前採文件人工驗收**，未執行原生 `openspec validate`，因此不能宣稱 CLI PASS。需要原生驗證時，可在另有 OpenSpec CLI 的環境，依官方文件使用：

```powershell
openspec --version
openspec list
openspec validate refactor-smart-parking-proposal
```

執行版本及可用參數需以當時官方 CLI 說明為準。此處列出建議命令，**不是本儲存庫已執行的紀錄**。

OpenSpec 官方文件：https://openspec.dev/
