<template>
  <div class="hello">
    <ul>
      <li v-for="todo in todos">
        <b>{{todo.title}}</b> ({{todo.project}})
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      todos: [{
        title: 'Todo A',
        project: 'Project A',
        done: false
      }, {
        title: 'Todo B',
        project: 'Project B',
        done: true
      }, {
        title: 'Todo C',
        project: 'Project C',
        done: false
      }, {
        title: 'Todo D',
        project: 'Project D',
        done: false
      }]
    }
  }
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
a {
  color: #42b983;
}
</style>
