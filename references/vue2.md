# Vue 2 審核規範

## 核心準則
- **Options API**: 確保 Data, Methods, Computed 結構清晰。
- **生命週期**: 正確使用 `mounted`, `destroyed` (而非 Vue 3 的 `unmounted`)。
- **響應式限制**: 注意 `Vue.set` 在處理新增屬性時的必要性。
- **Mixins**: 慎用 Mixins，避免命名衝突與來源不明的問題。

## 參考資料
- [Vue 2 官方文件](https://v2.vuejs.org/v2/guide/)
- [Vue 2 風格指南](https://v2.vuejs.org/v2/style-guide/)
