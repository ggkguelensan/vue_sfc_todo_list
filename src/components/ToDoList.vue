<template>
  <div class="todolist container">
      <p>todoitem 1</p>
      <p>todoitem 2</p>
      <p>todoitem 3</p>
      <p>todoitem 4</p>
  </div>
</template>

<script>
export default {
  name: 'ToDoList',
  data () {
    return {
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
</style>
