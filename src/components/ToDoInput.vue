<template>
  <div class="todoinput container">
    <input
      type="text"
      placeholder="TODO item input"
      v-model.trim="new_item_text"
      @keydown.enter="add_new_item"
    />
    <button :disabled="!new_item_text" @click="add_new_item">+</button>
  </div>
</template>

<script>
export default {
  name: 'ToDoInput',
  props: ['inputedtext'],
  data () {
    return {
      new_item_text: ''
    }
  },
  methods: {
    add_new_item () {
      if (this.new_item_text.trim()) {
        this.$emit('todo__input__add-new-item', { id: 0, text: this.new_item_text, active: true })
        this.new_item_text = ''
      }
    }
  }
}
</script>

<style scoped></style>
