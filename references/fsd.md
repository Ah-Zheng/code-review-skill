# Feature-Sliced Design (FSD) 架構審核
重點關注：
- **層級劃分 (Layers)**：檢查代碼是否正確歸類到 **app, pages, widgets, features, entities, shared** 這六個標準層級（注意：`processes` 層級已棄用，不應再使用）。
- **切片與段 (Slices & Segments)**：驗證 Slice 是否代表業務領域，Segment (ui, model, api, lib) 是否職責分離。
- **公共 API (Public API)**：確保每個 Slice 都有一個 `index.ts/js` 作為唯一出口，且嚴禁越過 Public API 直接存取內部檔案（Cross-imports）。
- **依賴方向 (Dependency Direction)**：驗證是否遵循「由上而下」的依賴規則（底層不能引用高層）。
- **職責邊界**：檢查 `features` 是否包含帶有副作用的交互邏輯，`entities` 是否僅包含業務實體與資料結構。

官方參考文件：[Feature-Sliced Design Documentation](https://feature-sliced.design/)
