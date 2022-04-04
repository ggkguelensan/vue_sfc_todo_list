<template>
  <div class="todoinput container">
    <input
      id="inputcom"
      type="text"
      placeholder="TODO item input"
      @keydown.enter="$emit('add-new-item')"
    />
    <button :disabled="is_disables" @click="$emit('add-new-item')">+</button>
  </div>
</template>

<script>
export default {
  name: "ToDoInput",
  props: ["inputedtext"],
  data() {
    return {
      is_disables: false
    };
  }
};
</script>

<style scoped></style>
