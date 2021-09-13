<template>
  <ul 
    class="list"
  >
  <todo-item
    v-for="todo of todos"
    :key="todo.id"
    :todo="todo"
    @deleteTodo="$emit('deleteTodo', todo.id)"
  />
  </ul>
</template>

<script>
import TodoItem from '@/components/TodoItem'

export default {
  name: 'todo-list',
  props: [
    'todos'
  ],
  components: {
    TodoItem
  }
}
</script>

<style scoped>
.list {
  padding: 0;
  margin: 0;
  list-style-type: none;
}
</style>