<template>
  <!-- 父组件通过 标签动态绑定数据 传递给子组件 子组件就可以通过props来拿到数据 -->
  <!-- 子组件触发父组件的方法 $emit -->
  <!-- event.$emit 兄弟之间的通信 event.on 绑定自定义事件 -->
  <!-- 在beforeDestroy 会做什么事情 做解绑自定义事件 否则就会造成内存泄漏 -->
  <div>
    <Input @add="addHandler" />
    <List :list="list"
          @delete="deleteHandler" />
  </div>
</template>

<script>
import Input from "./Input";
import List from "./List";

export default {
  components: {
    Input,
    List
  },
  data () {
    return {
      list: [
        {
          id: "id-1",
          title: "标题"
        }, {
          id: "id-2",
          title: "标题"
        }
      ]
    };
  },
  methods: {
    addHandler (title) {
      this.list.push({
        id: `id-${Date.now()}`,
        title
      })
    },
    deleteHandler (id) {
      this.list = this.list.filter(item => item.id !== id)
      console.log('index List', this.list)
    }
  },
  created () {
    console.log('index created');
  },
  mounted () {
    console.log('index mounted');
  },
  beforeUpdate () {
    console.log('index beforeUpdate')
  },
  updated () {
    console.log('index updated')
  },
  beforeDestroy () {
    console.log('index beforeDestroy')
  },
  destroyed () {
    console.log('destroyed')
  },
};
</script>

<style>
</style>