<template>
  <li class="todo__item container">
    <input
      type="checkbox"
      :checked="!item.active"
      @change="$emit('todo__item__set-item-status-by-id', item.id, !item.active)"
    />
    <p>{{ item.text }}</p>
    <button @click="$emit('todo__item__delete-item-by-id', item.id)">X</button>
  </li>
</template>

<script>
export default {
  name: 'ToDoItem',
  props: {
    item: Object
  },
  data () {
    return {}
  }
}
</script>

<style scoped>
li {
  padding: 10px;
  margin: 10px 0;
}
</style>
