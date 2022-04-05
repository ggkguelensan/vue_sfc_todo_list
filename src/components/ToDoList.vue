<template>
  <ul class="todo__list container">
    <ToDoItem
      @todo__item__delete-item-by-id="send_up_event_delete_item_by_id"
      @todo__item__set-item-status-by-id="send_up_event_set_item_status_by_id"
      v-for="item in todo_list"
      :item="item"
      :key="item.id"
    />
  </ul>
</template>

<script>
// multy-word component name
import ToDoItem from './ToDoItem'

export default {
  name: 'ToDoList',
  // detaild prop definition
  props: {
    todo_list: Array
  },
  components: {
    ToDoItem
  },
  data () {
    return {}
  },
  methods: {
    send_up_event_delete_item_by_id (id) {
      this.$emit('todo__item__delete-item-by-id', id)
    },
    send_up_event_set_item_status_by_id (id, active) {
      this.$emit('todo__item__set-item-status-by-id', id, active)
    }
  }
}
</script>

<style scoped>
ul {
  list-style-type: none;
  padding: 0;
}
</style>
