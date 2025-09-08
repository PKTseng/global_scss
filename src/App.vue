<template>
  <div class="container">
    <h1 class="title">SCSS 樣式測試</h1>

    <!-- 測試響應式斷點 -->
    <div class="responsive-box">響應式測試盒子</div>

    <!-- 測試顏色變數 -->
    <div class="color-test">
      <div class="primary">Primary Color</div>
      <div class="secondary">Secondary Color</div>
      <div class="success">Success Color</div>
      <div class="warning">Warning Color</div>
      <div class="error">Error Color</div>
    </div>

    <!-- 測試字體大小 -->
    <div class="font-test">
      <p class="font-sm">小字體 (14px)</p>
      <p class="font-base">基礎字體 (16px)</p>
      <p class="font-lg">大字體 (18px)</p>
      <p class="font-xl">超大字體 (24px)</p>
    </div>

    <!-- 測試間距 -->
    <div class="spacing-test">
      <div class="spacing-sm">小間距</div>
      <div class="spacing-md">中間距</div>
      <div class="spacing-lg">大間距</div>
    </div>
  </div>
</template>

<style lang="scss">
.container {
  padding: $spacing-lg;
  max-width: 800px;
  margin: 0 auto;
}

.title {
  font-size: $font-size-xl;
  color: $primary-color;
  margin-bottom: $spacing-lg;
  text-align: center;
}

// 測試響應式
.responsive-box {
  padding: $spacing-md;
  background-color: $secondary-color;
  color: white;
  text-align: center;
  border-radius: 4px;
  font-weight: bold;
  margin-bottom: 16px;

  @include xs {
    background-color: $success-color;
  }

  @include sm {
    background-color: $warning-color;
  }

  @include md {
    background-color: $error-color;
  }

  @include lg {
    background-color: $primary-color;
  }
}

// 測試顏色
.color-test {
  display: flex;
  gap: $spacing-sm;
  margin-bottom: $spacing-lg;
  flex-wrap: wrap;

  > div {
    padding: $spacing-md;
    color: white;
    border-radius: 4px;
    font-weight: bold;
    flex: 1;
    min-width: 120px;
    text-align: center;
  }

  .primary {
    background-color: $primary-color;
  }
  .secondary {
    background-color: $secondary-color;
  }
  .success {
    background-color: $success-color;
  }
  .warning {
    background-color: $warning-color;
    color: $text-color;
  }
  .error {
    background-color: $error-color;
  }
}

// 測試字體
.font-test {
  margin-bottom: $spacing-lg;

  .font-sm {
    font-size: $font-size-sm;
  }
  .font-base {
    font-size: $font-size-base;
  }
  .font-lg {
    font-size: $font-size-lg;
  }
  .font-xl {
    font-size: $font-size-xl;
    font-weight: bold;
  }
}

// 測試間距
.spacing-test {
  margin-bottom: $spacing-lg;

  > div {
    background-color: $primary-color;
    color: white;
    margin-bottom: $spacing-sm;
    border-radius: 4px;
  }

  .spacing-sm {
    padding: $spacing-sm;
  }
  .spacing-md {
    padding: $spacing-md;
  }
  .spacing-lg {
    padding: $spacing-lg;
  }
}
</style>
