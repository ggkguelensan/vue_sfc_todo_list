<template>
  <div class="todo__item container">
    <input type="checkbox" :checked="!item.active"/>
    <p>{{ item.text }}</p>
    <button @click="add ">X</button>
  </div>
</template>

<script>
export default {
  name: 'ToDoItem',
  props: ['item'],
  data () {
    return {}
  }
}
</script>

<style scoped>
li {
  display: inline-block;
  margin: 0 10px;
}
</style>
