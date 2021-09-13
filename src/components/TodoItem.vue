<template>
  <li>
    <div>
      <input 
        type="checkbox"
        @change="isCompleted"
      >
      <span
        :class="{completed: this.todo.completed}"
      >
        {{ todo.title }}
      </span>
    </div>
    <div>
      <my-button
        @click="$emit('deleteTodo', todo.id)"
      >
        Delete
      </my-button>
    </div>
  </li>
</template>

<script>
export default {
  name: 'todo-item',
  props: [
    'todo'
  ],
  methods: {
    isCompleted() {
      this.todo.completed = !this.todo.completed
    }
  }
}
</script>

<style>
li {
  display: flex;
  justify-content: space-between;
  margin: 10px 0;
}

.completed {
  color: teal;
  text-decoration: line-through;
}
</style>