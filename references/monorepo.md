# Monorepo (pnpm + Turbo) 審核規範

## 核心準則
- **相依性管理 (pnpm)**: 
    - 確保 `workspace:` 協定使用一致，避免引用到發佈後的版本而非原始碼。
    - 檢查是否有重複安裝的套件，應盡量提升至根目錄 `package.json`（若為全域開發工具）。
- **任務執行 (Turborepo)**:
    - 檢查 `turbo.json` 的 `pipeline` 配置，確保 `inputs` 與 `outputs` 定義正確，以極大化快取效率。
    - 避免在子專案中直接執行指令，應透過根目錄的 turbo 進入點。
- **Workspace 隔離**:
    - 檢查內部套件 (Internal Packages) 是否有循環引用。
    - 確保專案間的引用是透過 `package.json` 定義，而非相對路徑引用。

## 建議與預防建議
- **Phantom Dependencies**: 利用 pnpm 嚴格的 node_modules 結構，確保沒有引用到未宣告的套件（例如：避免在 Package A 中引用未在其 `package.json` 宣告的套件，即便該套件已存在於根目錄或其他 Package 中）。
- **Version Mismatch**: 使用 `pnpm manypkg check` 或類似工具確保各 workspace 間的同名套件版本一致。
- **Pruning**: 在部署階段，確保使用 `pnpm deploy --filter` 來減少不必要的檔案傳輸。

## 參考資料
- [pnpm Workspaces 官方文件](https://pnpm.io/workspaces)
- [Turborepo 官方文件](https://turbo.build/repo/docs)
- [Monorepo.tools (架構參考)](https://monorepo.tools/)
