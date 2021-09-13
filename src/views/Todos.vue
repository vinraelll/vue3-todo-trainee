<template>
  <div class="todos">
    <h1>Todo Application</h1>
    <hr>
    <todo-form 
      @createTodo="addTodo"
    />
    <hr>
    <loader
      v-if="isLoading"
    >
    </loader>
    <todo-list 
      class="list"
      :todos="todos"
      @deleteTodo="deleteTodo"
    />
    <div
      v-if="this.todos.length === 0 && this.isLoading === false"
    >
      There are no todos now. Completed em all, good job!
    </div>
  </div>
</template>

<script>
import TodoForm from '@/components/TodoForm'
import TodoList from '@/components/TodoList'

export default {
  components: {
    TodoForm,
    TodoList
  },
  data() {
    return {
      todos: [],
      isLoading: true
    }
  },
  methods: {
    addTodo(title) {
      if (!title) {
        alert('There must be something written in the field below. Give name for your task')
        return
      }

      const todo = {
        id: Date.now(),
        title: title,
        completed: false
      }

      this.todos.push(todo)
      
    },
    deleteTodo(id) {
      this.todos = this.todos.filter(todo => todo.id != id)
    }
  },
  mounted() {
    fetch('https://jsonplaceholder.typicode.com/todos/?_limit=3')
      .then(response => response.json())
      .then(json => {
        setTimeout(() => {
          this.todos = json
          this.isLoading = false
        }, 2000)
      })
  },
}
</script>

<style scoped>
.todos {
  max-width: 450px;
  margin: 0 auto;
  padding: 20px;
  border: 1px solid teal;
  border-radius: 10px;
}

.list {
  text-align: left;
}
</style>