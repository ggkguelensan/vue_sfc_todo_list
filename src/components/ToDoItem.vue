<template>
  <div class="todoitem container">
    <input type="checkbox" v-model="completed" @change="doneEdit" />
    <p>{{ item.text }}</p>
    <button>X</button>
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
