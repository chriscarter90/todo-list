<template>
  <div class="column todo-section">
    <todo-list :todos="sortedTodos"></todo-list>
    <create-todo @create-todo="createTodo"></create-todo>
    <sort-todos @sort-todos="sortTodos" :desc="sortDescending"></sort-todos>
  </div>
</template>

<script>
import CreateTodo from './CreateTodo'
import SortTodos from './SortTodos'
import TodoList from './TodoList'

export default {
  components: {
    CreateTodo,
    SortTodos,
    TodoList
  },
  props: ['todos'],
  data () {
    return {
      allTodos: this.todos,
      sortDescending: true
    }
  },
  methods: {
    createTodo (attrs) {
      this.allTodos.push(
        { ...attrs }
      )
    },
    sortTodos () {
      this.sortDescending = !this.sortDescending
    }
  },
  computed: {
    sortedTodos () {
      return Object.assign([], this.allTodos).sort((a, b) => {
        if (a.title.toLowerCase() > b.title.toLowerCase()) {
          return (this.sortDescending ? 1 : -1)
        }
        if (a.title.toLowerCase() < b.title.toLowerCase()) {
          return (this.sortDescending ? -1 : 1)
        }
        return 0
      })
    }
  }
}
</script>

<style></style>
