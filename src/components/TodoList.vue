<template>
  <div class="hello">
    <p>Completed Tasks: {{todos.filter(todo => {return todo.done === true}).length}}</p>
    <p>Pending Tasks: {{todos.filter(todo => {return todo.done === false}).length}}</p>
    <Todo v-on:delete-todo="deleteTodo" v-for="todo in todos" v-bind:todo="todo"></Todo>
  </div>
</template>

<script>
import Todo from './Todo'

export default {
  components: {
    Todo
  },
  props: ['todos'],
  methods: {
    deleteTodo(todo) {
      const todoIndex = this.todos.indexOf(todo);
      this.todos.splice(todoIndex, 1);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
