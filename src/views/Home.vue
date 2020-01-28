<template>
  <div class="home">
    <div class="components-container"></div>
    <div class="center-container"></div>
    <div class="config-container"></div>
  </div>
</template>

<script>

export default {
  name: 'home'
}
</script>

<style lang="scss" scoped>
.home {
  display: flex;
  width: 100%;
  height: 100%;
  overflow: hidden;
  .components-container {
    flex: none;
    width: 250px;
    height: 100%;
  }
  .center-container {
    flex: 1;
    width: 100%;
    height: 100%;
    border-left: 1px solid #e0e0e0;
    border-right: 1px solid #e0e0e0;
  }
  .config-container {
    flex: none;
    width: 250px;
    height: 100%;
  }
}
</style>
