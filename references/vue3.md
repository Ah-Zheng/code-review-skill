# Vue 3 審核規範

## 核心準則
- **Composition API**: 優先使用 `<script setup>` 語法。
- **Reactivity**: 正確區分 `ref` 與 `reactive` 的使用場景。
- **生命週期**: 使用 `onMounted`, `onUnmounted` 等組合式 API。
- **Fragments**: 利用 Vue 3 支援多根節點的特性，減少不必要的平鋪 div。
- **Teleport & Suspense**: 視需求使用新組件提升 UX 與 DOM 結構。

## 參考資料
- [Vue 3 官方文件](https://vuejs.org/guide/introduction.html)
- [Vue 3 風格指南](https://vuejs.org/style-guide/)
