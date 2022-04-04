<template>
  <div class="todoitem container">
      <p>{{item.text}}</p>
      <button>X</button>
  </div>
</template>

<script>
export default {
  name: 'ToDoItem',
  props: ['item'],
  data () {
    return {
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
li {
  display: inline-block;
  margin: 0 10px;
}
</style>
