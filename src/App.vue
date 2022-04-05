<template>
  <div id="app">
    <ToDo :api_href="api.todo_api" />
  </div>
</template>

<script>
import ToDo from './components/ToDo'

export default {
  name: 'App',
  data () {
    return {
      api: {
        todo_api: 'https://my-json-server.typicode.com/falk20/demo/todos'
      }
    }
  },
  components: {
    ToDo
  }
}
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
