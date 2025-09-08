<template>
  <div class="container">
    <h1>響應式斷點測試</h1>
    <div class="box">我會隨著螢幕寬度改變背景顏色！</div>
  </div>
</template>

<style lang="scss">
.container {
  text-align: center;
  padding: 20px;
}

.box {
  padding: 20px;
  background-color: lightblue;

  @include xs {
    background-color: lightgreen;
  }
  @include sm {
    background-color: lightcoral;
  }
  @include md {
    background-color: lightyellow;
  }
  @include lg {
    background-color: lightpink;
  }
}
</style>
