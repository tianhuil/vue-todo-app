<template>
  <div class="hello">
    <p>Completed Tasks: {{todos.filter(todo => {return todo.done === true}).length}}</p>
    <p>Pending Tasks: {{todos.filter(todo => {return todo.done === false}).length}}</p>
    <Todo v-for="todo in todos" :todo="todo"></Todo>
  </div>
</template>

<script>
import Todo from './Todo'

export default {
  components: {
    Todo
  },
  props: ['todos']
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
