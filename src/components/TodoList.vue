<template>
  <div class="hello">
    <div class='ui centered card'>
      <div class='ui three button basic attached buttons'>
        <div class='ui top attached basic button'
             v-bind:class="{active: filter=='all'}"
             v-on:click="setFilter('all')">
          All ({{todos.length}})
        </div>
        <div class='ui top attached basic button'
             v-bind:class="{active: filter=='done'}"
             v-on:click="setFilter('done')">
          Done ({{doneTodos.length}})
        </div>
        <div class='ui top attached basic button'
             v-bind:class="{active: filter=='active'}"
             v-on:click="setFilter('active')">
          Active ({{activeTodos.length}})
        </div>
      </div>
    </div>
    <Todo v-on:delete-todo="deleteTodo"
          v-on:complete-todo="completeTodo"
          v-for="todo in displayTodos"
          v-bind:todo="todo"/>
  </div>
</template>

<script>
import Todo from './Todo'

export default {
  components: {
    Todo
  },
  data () {
    return {
      filter: 'all'
    }
  },
  props: ['todos'],
  methods: {
    completeTodo (todo) {
      const todoIndex = this.todos.indexOf(todo)
      this.todos[todoIndex].done = true
    },
    deleteTodo (todo) {
      const todoIndex = this.todos.indexOf(todo)
      this.todos.splice(todoIndex, 1)
    },
    setFilter (filter) {
      this.filter = filter
    }
  },
  computed: {
    displayTodos: function () {
      switch (this.filter) {
        case 'all':
          return this.todos
        case 'done':
          return this.doneTodos
        case 'active':
          return this.activeTodos
      }
    },
    doneTodos: function () {
      return this.todos.filter(todo => { return todo.done === true })
    },
    activeTodos: function () {
      return this.todos.filter(todo => { return todo.done === false })
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
