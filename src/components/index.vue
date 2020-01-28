<template>
  <div class="home">
    <div class="components-container">
      <div class="components-title">基础组件</div>
      <draggable tag="div"
                 :list="basicComponents"
                 class="components-row"
                 v-bind="{group:{ name:'people', pull:'clone',put:false},sort:false, ghostClass: 'ghost'}">
        <div class="component-item"
             v-for="(component, index) in basicComponents"
             :key="index">
          <div class="grid-content">{{component.label}}</div>
        </div>
      </draggable>

    </div>
    <div class="center-container">
      <div class="btn-list"></div>
      <div class="form-container">
        <div class="drag-form-list"></div>
      </div>
    </div>
    <div class="config-container"></div>
  </div>
</template>

<script>
import Draggable from 'vuedraggable'
import { basicComponents } from './componentsConfig'
export default {
  name: 'asp-form-design',
  data () {
    return {
      basicComponents
    }
  },
  components: {
    Draggable
  }
}
</script>

<style lang="scss" scoped>
$primary-color: #409eff;
$primary-background-color: #ecf5ff;
.home {
  display: flex;
  width: 100%;
  height: 100%;
  overflow: hidden;
  .components-container {
    flex: none;
    width: 250px;
    height: 100%;
    padding: 15px 10px;
    background: #fff;
    .components-title {
      font-size: 14px;
      margin-bottom: 10px;
    }
    .components-row {
      display: flex;
      flex-wrap: wrap;
      .component-item {
        width: 50%;
        padding: 0 5px;
        .grid-content {
          width: 100%;
          font-size: 12px;
          display: block;
          line-height: 28px;
          position: relative;
          float: left;
          left: 0;
          overflow: hidden;
          text-overflow: ellipsis;
          white-space: nowrap;
          color: #333;
          cursor: move;
          background-color: #f4f6fc;
          border: 1px solid #f4f6fc;
          text-align: center;
          margin-bottom: 10px;
          &:hover {
            color: $primary-color;
            border: 1px dashed $primary-color;
          }
        }
      }
    }
  }
  .center-container {
    flex: 1;
    width: 100%;
    height: 100%;
    border-left: 1px solid #e0e0e0;
    border-right: 1px solid #e0e0e0;
    overflow: hidden;
    .btn-list {
      width: 100%;
      height: 45px;
      display: flex;
      align-items: center;
      text-align: right;
      background: #fff;
      border-bottom: 2px solid #e4e7ed;
    }
    .form-container {
      overflow-y: auto;
      width: 100%;
      height: 100%;
      padding: 10px;
      .drag-form-list {
        background: #fff;
        min-height: 100%;
        border: 1px dashed #999;
      }
    }
  }
  .config-container {
    flex: none;
    width: 300px;
    height: 100%;
    background: #fff;
  }
}
</style>
