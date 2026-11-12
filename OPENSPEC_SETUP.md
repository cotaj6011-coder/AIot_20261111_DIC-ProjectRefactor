# OpenSpec 遠端版設定說明

## 本次已提交的項目
- `openspec/config.yaml`：專題 context 與規格撰寫準則。
- `.agents/skills/openspec-*/SKILL.md`：Codex 使用的六項 OpenSpec core Skills。
- `.github/skills/openspec-*/SKILL.md`：GitHub Copilot 使用的六項 OpenSpec core Skills。

上述 SKILL.md 取自 OpenSpec 官方來源 `Fission-AI/OpenSpec/skills`。此步驟是**將 Skills 與設定檔安置到 GitHub 遠端 Repository**；不是在 GitHub 伺服器安裝常駐 CLI，也不能證明 Windows 本機已安裝。

## Windows 本機正式初始化

請先 `git pull` 取得遠端檔案，從 VS Code 的專案根目錄 PowerShell 執行：

```powershell
# 官方獨立安裝器；執行前可先查看腳本內容
irm https://openspec.dev/cli/install.ps1 | iex
openspec --version

# 在專案根目錄進行原生初始化／同步
openspec init --tools codex,github-copilot
openspec list
```

若已有 OpenSpec CLI，可略過安裝，直接執行初始化。官方 init 可能更新本專案中的 Skill 或 command 檔案；執行後請使用 `git status` 檢查變更並決定是否提交。重新載入 VS Code / Copilot Chat 或 Codex 後，Codex 可使用 `$openspec-propose`，Copilot 依實際產生的 skill/指令操作。

## 下一步：本次作業
安裝完成後，以 `refactor-smart-parking-proposal` 為變更主題，依序產生 proposal / specs / design / tasks，重構 Introduction 與 Related Work，保留 Before/After 證據；不可把技能檔安裝視為整份作業驗收通過。

官方文件：
- https://openspec.dev/docs/installation
- https://github.com/Fission-AI/OpenSpec/blob/main/docs/supported-tools.md
