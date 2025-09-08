# SCSS 架構說明

## 文件結構

```
src/styles/
├── main.scss          # 主入口文件 (全域樣式)
├── _global.scss       # Vite 全域導入文件 (變數和 mixins)
├── _variables.scss    # 變數定義
├── _mixins.scss       # Mixins 和函數
├── _base.scss         # 基礎樣式 (reset, typography)
├── _layout.scss       # 佈局相關 (grid, containers)
├── _components.scss   # UI 組件樣式
├── _utilities.scss    # 工具類
└── pages/            # 頁面特定樣式
    ├── _home.scss
    └── _about.scss
```

### 文件說明

- **`main.scss`**: 主入口文件，在 `main.ts` 中導入，提供全域基礎樣式
- **`_global.scss`**: Vite 專用文件，通過 `additionalData` 讓變數和 mixins 在所有組件中可用

## 使用方式

### 1. 全域樣式

所有 SCSS 變數、mixins 都通過 `main.scss` 自動導入，可在任何 Vue 組件中直接使用：

```vue
<style lang="scss" scoped>
.my-component {
  color: $primary-color;

  @include respond-to(md) {
    padding: 2rem;
  }
}
</style>
```

### 2. 添加新樣式

- **變數**: 添加到 `_variables.scss`
- **Mixins**: 添加到 `_mixins.scss`
- **組件樣式**: 添加到 `_components.scss`
- **頁面樣式**: 在 `pages/` 資料夾創建新文件

### 3. 匯入順序

main.scss 中的匯入順序很重要：

1. 外部函式庫
2. Sass 工具
3. 變數
4. Mixins
5. 基礎樣式
6. 佈局
7. 組件
8. 頁面樣式
9. 工具類

## 可用的響應式斷點

- `xs`: 375px+
- `sm`: 768px+
- `md`: 1024px+
- `lg`: 1440px+
- `xl`: 1920px+
