# OpenSpec CLI 實際驗證紀錄

**驗證日期：2026-11-19（Asia/Taipei）**  
**Change：**`refactor-smart-parking-proposal`  
**結果：PASS，exit code 0；1 change 通過、0 失敗、0 issues。**

## 安裝來源與版本

- 官方 [OpenSpec v2.1.0 release](https://github.com/Fission-AI/OpenSpec/releases/tag/v2.1.0)，發布於 2026-11-17。
- 套件：[openspec-windows-x64.zip](https://github.com/Fission-AI/OpenSpec/releases/download/v2.1.0/openspec-windows-x64.zip)。
- 官方校驗：[SHA256SUMS](https://github.com/Fission-AI/OpenSpec/releases/download/v2.1.0/SHA256SUMS)。下載 ZIP 的 SHA256 與官方值一致：

```text
446a66b810bf263dffd3a10811224b4c742673bf4eba019ec878009bb7d02b8a
```

採專案內 standalone 安裝於 `.tools/openspec-2.1.0/`，未新增 branch、clone、commit 或 push，也未更動系統 PATH。本機已有 Node v24.22.3；此 standalone 執行方式不依賴 Node/npm。`.tools/` 執行檔與下載包屬本機工具，不列入作業交付。

## 實際執行與結果

在專案根目錄執行下列命令；命令中完整相對路徑是為了使用本次固定版本，而非假設 CLI 已加入 PATH。

```powershell
& '.\.tools\openspec-2.1.0\openspec.exe' --version
# 2.1.0

& '.\.tools\openspec-2.1.0\openspec.exe' list
# refactor-smart-parking-proposal

& '.\.tools\openspec-2.1.0\openspec.exe' status --change refactor-smart-parking-proposal --json
# schemaName: spec-driven
# proposal / specs / design / tasks: done

& '.\.tools\openspec-2.1.0\openspec.exe' validate refactor-smart-parking-proposal --strict --no-interactive --json
# exit code 0
```

原始驗證輸出保存在 [OPENSPEC_CLI_VALIDATION.json](OPENSPEC_CLI_VALIDATION.json)。關鍵欄位：

```json
{
  "id": "refactor-smart-parking-proposal",
  "type": "change",
  "valid": true,
  "issues": []
}
```

CLI 的 `status` 以四種規劃文件存在性確認 planning complete；這不代表所有 `tasks.md` 核取項已完成。H1 重驗、H2/H3 研究實驗與課程平台提交仍依各自證據紀錄。

## 驗證範圍

本次 CLI 檢查 OpenSpec Change、Delta Spec 及其 Requirement／Scenario 格式。原始 **9 項 Requirement／9 個 Scenario** 保留，沒有以刪除規格換取 PASS。人工證據對照另見 [OPENSPEC_MANUAL_VERIFICATION.md](OPENSPEC_MANUAL_VERIFICATION.md)。

CLI PASS **不等於**來源論文結果重現、模型效能通過、系統正式部署或 iLearning 已提交；這些項目各自列於 [ACCEPTANCE.md](ACCEPTANCE.md)。
