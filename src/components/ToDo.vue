<template>
  <div class="todo container">
    <h1>TODO list</h1>
    <ToDoInput/>
    <ToDoCntl/>
    <ToDoList :todolist="todolist"/>
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
      todolist: [
        {id: 0, text: 'Uno'},
        {id: 1, text: 'Duo'},
        {id: 2, text: 'Tre'},
        {id: 3, text: 'Apple'},
        {id: 4, text: 'Hello'}
      ]
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
