<template>
  <div class="todocntl container">
    <button @click="$emit('set-state')">Active</button>
    <button>All</button>
    <button>Completed</button>
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

<style scoped></style>
