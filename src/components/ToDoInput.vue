<template>
  <div class="todoinput container">
      <input type="text" placeholder="TODO item input" @keydown.enter="new_item">
      <button :disabled="is_disables">+</button>
  </div>
</template>

<script>
export default {
  name: 'ToDoInput',
  methods: {
    new_item: function () {
    }
  },
  data () {
    return {
      is_disables: true
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
