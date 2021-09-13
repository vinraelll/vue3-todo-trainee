<template>
  <form 
    class="form"
    @submit.prevent
  >
    <my-input 
      v-model="title"
      placeholder="Create new task!"
    />
    <my-button
      class="button"
      type="submit"
      @click="getTodoName"
    >
      Create task
    </my-button>
  </form>
</template>

<script>


export default {
  name: 'todo-form',
  emits: ['createTodo'],
  data() {
    return {
      title: ''
    }
  },
  methods: {
    getTodoName() {
      this.$emit('createTodo', this.title)
      this.title = ''
    }
  }
}
</script>

<style scoped>
.form {
  display: flex;
  justify-content: space-between;
}

.button {
  width: 100%;
}
</style>