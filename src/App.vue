<template>
  <div id="app">
    <div class="ui three column doubling stackable grid container">
      <todo-container :key="1" :todos="list1"></todo-container>
      <todo-container :key="2" :todos="list2"></todo-container>
      <todo-container :key="3" :todos="list3"></todo-container>
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
      list1: [{ title: 'a', project: 'a', done: false }],
      list2: [{ title: 'd', project: 'd', done: false }, { title: 'b', project: 'b', done: false }],
      list3: [{ title: 'c', project: 'c', done: false }]
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
