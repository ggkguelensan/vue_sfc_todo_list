<template>
  <div class="todolist container">
    <ToDoItem v-for="item in todolist" :item="item" :key="item.id" />
  </div>
</template>

<script>
import ToDoItem from "./ToDoItem";
export default {
  name: "ToDoList",
  props: ["todolist"],
  components: {
    ToDoItem: ToDoItem
  },
  data() {
    return {};
  }
};
</script>

<style scoped>
ul {
  list-style-type: none;
  padding: 0;
}
</style>
