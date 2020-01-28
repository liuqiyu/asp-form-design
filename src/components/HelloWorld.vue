<template>
  <div class="hello">
    <el-row :gutter="20">
      <el-col :span="6">
        <draggable v-model="myArray"
                   v-bind="{group:{ name:'people', pull:'clone',put:false},sort:false, ghostClass: 'ghost'}"
                   :move="handleMove">
          <transition-group>
            <div class="item"
                 v-for="element in myArray"
                 :key="element.id">
              {{element.name}}
            </div>
          </transition-group>
        </draggable>
        {{myArray}}
      </el-col>
      <el-col :span="12">
        {{data}}
        <draggable class=""
                   v-model="data.list"
                   v-bind="{group:'people', ghostClass: 'ghost',animation: 200, handle: '.drag-widget'}"
                   @add="handleWidgetAdd">
          <transition-group name="fade"
                            tag="div"
                            style="height: 300px; background: pink"
                            class="widget-form-list">
            <div v-for="(element, index) in data.list"
                 :key="element.id">
              <div class="item"
                   :class="{active: selectKey === index}"
                   @click.stop="handleSelectWidget(index)">
                {{element.name}}
              </div>
              <div class="widget-view-drag widget-col-drag"
                   v-if="selectKey === index">
                <i class="iconfont icon-drag drag-widget"></i>
              </div>
            </div>
          </transition-group>
        </draggable>
      </el-col>
    </el-row>

  </div>
</template>

<script>
import draggable from 'vuedraggable'
export default {
  name: 'HelloWorld',
  data () {
    return {
      myArray: [
        {
          id: 1,
          name: '你好'
        },
        {
          id: 2,
          name: '再见'
        },
        {
          id: 3,
          name: '我的'
        },
        {
          id: 4,
          name: '爱情'
        }
      ],
      data: {
        list: []
      },
      selectKey: null
    }
  },
  components: {
    draggable
  },
  methods: {
    handleSelectWidget (index) {
      console.log(index)
      this.selectKey = index
    },
    handleMove () {
      return true
    },
    handleWidgetAdd (e) {
      console.log(e)
    }
  }
}
</script>

<style scoped lang="scss">
.item {
  padding: 10px;
  color: #333;
  border: 1px solid #f4f6fc;
  margin-bottom: 10px;
  cursor: move;
  background: #f4f6fc;
  &:hover {
    border: 1px dashed #409eff;
    color: #409eff;
  }
}
.active {
  border: 1px solid red;
}

.ghost {
  background: red;
  border: 2px solid blue;
  position: relative;

  &::after {
    background: blue;
  }
}
</style>
