<template>
  <div id="app">
    <div class="ui three column doubling stackable grid container">
      <todo-container v-for="(list, index) in lists" :key="index" :todos="list"></todo-container>
    </div>
  </div>
</template>

<script>
import TodoContainer from './components/TodoContainer'

export default {
  name: 'app',
  components: {
    TodoContainer
  },
  data () {
    return {
      lists: [
        [
          { title: 'a', project: 'a', done: false }
        ],
        [
          { title: 'd', project: 'd', done: false },
          { title: 'b', project: 'b', done: false }
        ],
        [
          { title: 'c', project: 'c', done: false }
        ]
      ]
    }
  }
}
</script>

<style>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
</style>
