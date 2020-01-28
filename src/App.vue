<template>
  <div id="app">
    <el-header class="asp-header">
      <h1 class="logo">卓望-表单设计器</h1>
    </el-header>
    <el-container class="asp-container">
      <router-view />
    </el-container>
    <el-footer class="asp-footer">Powered by asp-form-design</el-footer>
  </div>
</template>

<style lang="scss">
html,
body,
#app {
  width: 100%;
  height: 100%;
  overflow: hidden;
}
*,
:after,
:before {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}

#app {
  background: #f5f7fa;
  display: flex;
  flex-direction: column;
  .asp-header {
    background-color: #1278f6;
    display: flex;
    flex: none;
    justify-content: space-between;
    align-items: center;
    .logo {
      color: rgba(255, 255, 255, 0.9);
      font-size: 20px;
    }
  }
  .asp-container {
    flex: 1;
    height: 100%;
  }
  .asp-footer {
    flex: none;
    height: 30px !important;
    line-height: 30px;
    border-top: 1px solid #e0e0e0;
    font-size: 12px;
    text-align: center;
    color: #409eff;
    background: #fafafa;
  }
}
</style>
