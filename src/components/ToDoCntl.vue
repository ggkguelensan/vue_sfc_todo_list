<template>
  <div class="todo__cntl container">
    <button @click="$emit('todo__cntl__set-state', 'active')">Active</button>
    <button @click="$emit('todo__cntl__set-state', 'all')">All</button>
    <button @click="$emit('todo__cntl__set-state', 'completed')">Completed</button>
  </div>
</template>

<script>
export default {
  name: 'ToDoCntl',
  data () {
    return {}
  }
}
</script>

<style scoped>
.button {
  border: none;
  border-radius: 2px;
}

.button-close {
  background-color: red;
}
</style>
