<template>
  <div class="todo container">
    <h1>TODO component</h1>
    <ToDoInput @todo__input__add-new-item="add_new_item"/>
    <ToDoCntl @todo__cntl__set-state="set_cntl_state"/>
    <ToDoList :todo_list="todo_list_filtered" />
  </div>
</template>

<script>
import ToDoList from './ToDoList'
import ToDoInput from './ToDoInput'
import ToDoCntl from './ToDoCntl'

export default {
  name: 'ToDo',
  props: ['api_href'],
  components: {
    // компонент принимаюйщий ввод из формы
    ToDoInput,
    // компонент выставляющий состояние отображение item'ов
    ToDoCntl,
    // компонет отображающий список item'ов
    ToDoList
  },
  data () {
    return {
      // перепишется при вызове created
      todo_list: [
        { id: 0, text: 'Item text 1', active: true },
        { id: 1, text: 'Item text 2', active: false },
        { id: 2, text: 'Item text 3', active: true },
        { id: 3, text: 'Item text 4', active: false },
        { id: 4, text: 'Item text 5', active: true }
      ],
      cntl_state: 'all'
    }
  },
  methods: {
    // handler обрабатывающий создание нового item и добавление нового item в список todo_list
    add_new_item (item) {
      this.todo_list.push({
        id: this.todo_list.length + 1,
        text: item.text,
        active: item.active
      })
    },
    set_cntl_state (state) {
      this.cntl_state = state
    }
  },
  computed: {
    todo_list_filtered () {
      let result = []
      if (this.cntl_state === 'all') {
        result = this.todo_list
      } else if (this.cntl_state === 'active') {
        result = this.todo_list.filter(item => item.active === true)
      } else {
        result = this.todo_list.filter(item => item.active === false)
      }
      return result
    }
  },
  created () {
    fetch(this.api_href)
      .then(response => response.json())
      .then(data => {
        this.todo_list = data
      })
  }
}
</script>

<style scoped>
h1 {
  font-weight: normal;
}
</style>
