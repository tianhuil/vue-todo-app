<template>
  <div class="hello">
    <ul>
      <p>Completed Tasks: {{todos.filter(todo => {return todo.done === true}).length}}</p>
      <p>Pending Tasks: {{todos.filter(todo => {return todo.done === false}).length}}</p>
      <li v-for="todo in todos">
        <div v-bind:class="{done: todo.done}">
          <b>{{todo.title}}</b> ({{todo.project}})
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: ['todos']
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  margin: 0 10px;
}
div.done {
  text-decoration: line-through;
  color: #b0b0b0;
}
</style>
