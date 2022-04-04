<template>
  <div class="todo container">
    <h1>TODO list</h1>
    <ToDoInput/>
    <ToDoCntl/>
    <ToDoList/>
  </div>
</template>

<script>
import ToDoList from './ToDoList'
import ToDoInput from './ToDoInput'
import ToDoCntl from './ToDoCntl'

export default {
  name: 'ToDo',
  components: {
    ToDoInput,
    ToDoCntl,
    ToDoList
  },
  data () {
    return {
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1 {
  font-weight: normal;
}
</style>
