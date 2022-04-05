<template>
  <div class="todo__list container">
    <ToDoItem v-for="item in todo_list" :item="item" :key="item.id" />
  </div>
</template>

<script>
import ToDoItem from './ToDoItem'
export default {
  name: 'ToDoList',
  props: ['todo_list'],
  components: {
    ToDoItem
  },
  data () {
    return {}
  }
}
</script>

<style scoped>
ul {
  list-style-type: none;
  padding: 0;
}
</style>
