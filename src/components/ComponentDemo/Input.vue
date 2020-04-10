<template>
  <div>
    <input type="text"
           v-model="title" />
    <button @click="addTitle">add</button>
  </div>
</template>

<script>
import event from './event'

export default {
  data () {
    return {
      title: ''
    }
  },
  methods: {
    addTitle () {
      // 调用父组件的事件
      this.$emit('add', this.title)

      // 调用自定义事件
      event.$emit('onAddTitle', this.title)

      this.title = ''
    }
  },
  created () {
    console.log('Input created');
  },
  mounted () {
    console.log('Input mounted');
  },
  beforeUpdate () {
    console.log('Input beforeUpdate')
  },
  updated () {
    console.log('Input updated')
  },
  beforeDestroy () {
    console.log('Input beforeDestroy')
  },
  destroyed () {
    console.log('Input destroyed')
  },
}
</script>

<style>
</style>