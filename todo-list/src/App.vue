<template>
  <div id="app">
    <todoitem/>
    <todolist/>
  </div>
</template>

<script>
import Todoitem from './components/Todoitem.vue'
import Todolist from './components/Todolist.vue'

export default {
  name: 'App',
  components: {
    Todoitem,
    Todolist
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin-top: 60px;
}
</style>
