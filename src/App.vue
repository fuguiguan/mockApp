<template>
  <div id="app">
    hello
    <div v-for="(item,index) in items.list" :key="index">
      {{item.id}}
    </div>
  </div>
</template>

<script>
import Mock from 'mockjs'
export default {
  name: 'App',
  components: {
  },
  data() {
    return {
      items: ''
    }
  },
  mounted() {
    var datas = Mock.mock({
        // 属性 list 的值是一个数组，其中含有 1 到 10 个元素
        'list|1-10': [{
            // 属性 id 是一个自增数，起始值为 1，每次增 1
            'id|+1': 1
        }]
    })
    this.items = datas
    console.log(datas);
    
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
