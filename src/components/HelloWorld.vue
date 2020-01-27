<template>
  <div class="hello">
    <draggable v-model="myArray"
               v-bind="{group:{ name:'people', pull:'clone',put:false},sort:false, ghostClass: 'ghost'}">
      <transition-group>
        <div class="item"
             v-for="element in myArray"
             :key="element.id">
          {{element.name}}
        </div>
      </transition-group>
    </draggable>
    {{
      myArray
    }}
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
      ]
    }
  },
  components: {
    draggable
  }
}
</script>

<style scoped lang="scss">
.item {
  border: 1px dotted #333;
  padding: 10px;
  background: pink;
}
</style>
