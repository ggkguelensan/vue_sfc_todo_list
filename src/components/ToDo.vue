<template>
  <div class="todo container">
    <h1>TODO component</h1>
    <ToDoInput @todo__input__add-new-item="add_new_item"/>
    <ToDoCntl @todo__cntl__set-state="set_cntl_state"/>
    <ToDoList
    @todo__item__delete-item-by-id="delete_item_by_id"
    @todo__item__set-item-status-by-id="set_item_status_by_id"
    :todo_list="todo_list_filtered"
    />
  </div>
</template>

<script>
import ToDoList from './ToDoList'
import ToDoInput from './ToDoInput'
import ToDoCntl from './ToDoCntl'

function errorHandler (response) {
  if (!response.ok) {
    throw Error(response.status)
  }
  return response
}

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
        { id: 1, text: 'Fetch error item text 1', active: true },
        { id: 2, text: 'Fetch error item text 2', active: false },
        { id: 3, text: 'Fetch error item text 3', active: true },
        { id: 4, text: 'Fetch error item text 4', active: false },
        { id: 5, text: 'Fetch error item text 5', active: true }
      ],
      cntl_state: 'all',
      last_id: 5
    }
  },
  methods: {
    // handler обрабатывающий создание нового item и добавление нового item в список todo_list
    add_new_item (item) {
      this.last_id++
      this.todo_list.push({
        id: this.last_id,
        text: item.text,
        active: item.active
      })
    },
    set_cntl_state (state) {
      this.cntl_state = state
    },
    delete_item_by_id (id) {
      this.todo_list = this.todo_list.filter(item => item.id !== id)
    },
    set_item_status_by_id (id, active) {
      this.todo_list.find(item => item.id === id).active = active
    }
  },
  computed: {
    todo_list_filtered () {
      if (this.cntl_state === 'active') return this.todo_list.filter(item => item.active === true)
      if (this.cntl_state === 'completed') return this.todo_list.filter(item => item.active === false)
      return this.todo_list
    }
  },
  created () {
    if (this.api_href) {
      fetch(this.api_href)
        .then(errorHandler)
        .then(responce => responce.json())
        .then(data => {
          this.todo_list = data
          this.last_id = data.length
        })
        .catch(error => console.log(error))
    }
  }
}
</script>

<style scoped>
h1 {
  font-weight: normal;
}
</style>
