# TypeScript 審核規範

## 核心準則
- **型別安全**: 
    - 避免使用 `any`，應優先使用 `unknown` 或具體的 `interface`/`type`。
    - 確保 `tsconfig.json` 開啟 `strict: true`（或至少 `noImplicitAny`）。
- **重構與並用 (JS/TS Migration)**:
    - 在 JS/TS 並存專案中，確保 TS 檔案不直接引用未經宣告的 JS 模組（應提供 `.d.ts` 或使用 `allowJs`）。
    - 檢查是否有過度使用 `@ts-ignore` 或 `@ts-nocheck` 的情況。
- **介面設計**:
    - 優先使用 `interface` 定義物件結構，`type` 定義聯集 (Union) 或交叉 (Intersection) 型別。
    - 確保 Enum 的使用符合專案慣例（建議優先考慮 Union Types 或 Const Enum）。

## 建議與預防建議
- **Utility Types**: 善用 `Partial`, `Pick`, `Omit`, `Record` 等內建工具型別減少重複定義。
- **Type Guard**: 針對不確定型別的變數，應使用 `is` 關鍵字進行型別守衛。
- **Explicit Return Types**: 導出的函數應明確宣告回傳型別，以提升代碼可讀性與 IDE 效能。

## 參考資料
- [TypeScript 官方文件](https://www.typescriptlang.org/docs/)
- [TypeScript 風格指南 (Google)](https://google.github.io/styleguide/tsguide.html)
- [Clean Code TypeScript](https://github.com/labs42io/clean-code-typescript)
