<template>
  <div>
    <ul>
      <li v-for="item in list"
          :key="item.id">
        {{item.title}}
        {{item.id}}
        <button @click="deleteItem(item.id)">删除</button>
      </li>
    </ul>
  </div>
</template>

<script>
import event from './event'

export default {
  props: {
    list: {
      type: Array,
      default () {
        return []
      }
    }
  },
  data () {
    return {

    }
  },
  methods: {
    deleteItem (id) {
      this.$emit('delete', id)
    },
    addTitleHandler (title) {
      console.log('on add title', title)
    }
  },
  created () {
    console.log('List created');
  },
  mounted () {
    console.log('List mounted');
    event.$on('onAddTitle', this.addTitleHandler)
  },
  beforeUpdate () {
    console.log('List beforeUpdate')
  },
  updated () {
    console.log('List updated')
  },
  beforeDestroy () {
    console.log('List beforeDestroy')
  },
  destroyed () {
    console.log('List destroyed')
  },
}
</script>