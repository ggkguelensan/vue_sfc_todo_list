<template>
  <div class="todo container">
    <h1>TODO list</h1>
    <ToDoInput />
    <ToDoCntl />
    <ToDoList :todolist="todolist" />
  </div>
</template>

<script>
import ToDoList from "./ToDoList";
import ToDoInput from "./ToDoInput";
import ToDoCntl from "./ToDoCntl";

export default {
  name: "ToDo",
  components: {
    ToDoInput,
    ToDoCntl,
    ToDoList
  },
  data() {
    return {
      inputed_text: "",
      todolist: [
        { id: 0, text: "Item text 1", active: true },
        { id: 1, text: "Item text 2", active: true },
        { id: 2, text: "Item text 3", active: true },
        { id: 3, text: "Item text 4", active: true },
        { id: 4, text: "Item text 5", active: true }
      ],
      cntl_state: "all"
    };
  },
  methods: {
    add_item(text) {
      this.todolist.push({
        id: this.todolist.length + 1,
        text: text,
        active: false
      });
    }
  }
};
</script>

<style scoped>
h1 {
  font-weight: normal;
}
</style>
