<template>
  <div>
    <p>Completed Tasks: {{ completedTasks }}</p>
    <p>Pending Tasks: {{ pendingTasks }}</p>
    <todo
      v-for="todo in todos"
      :todo="todo"
      :key="todo.name"
      @complete-todo="completeTodo"
      @uncomplete-todo="uncompleteTodo"
      @delete-todo="deleteTodo">
    </todo>
  </div>
</template>

<script type = "text/javascript" >
import Todo from './Todo'

export default {
  props: ['todos'],
  data () {
    return {
      allTodos: this.todos
    }
  },
  components: {
    Todo
  },
  methods: {
    completeTodo (todo) {
      const todoIndex = this.allTodos.indexOf(todo)
      this.allTodos[todoIndex].done = true
    },
    uncompleteTodo (todo) {
      const todoIndex = this.allTodos.indexOf(todo)
      this.allTodos[todoIndex].done = false
    },
    deleteTodo (todo) {
      const todoIndex = this.allTodos.indexOf(todo)
      this.allTodos.splice(todoIndex, 1)
    }
  },
  computed: {
    completedTasks () {
      return this.allTodos.filter(todo => { return todo.done }).length
    },
    pendingTasks () {
      return this.allTodos.filter(todo => { return !todo.done }).length
    }
  }
}
</script>

<style> </style>
