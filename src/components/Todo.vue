<template>
  <div v-bind:class="{done: todo.done}">
    <b>{{todo.title}}</b> ({{todo.project}})
  </div>
</template>

<script type="text/javascript">
  export default {
    props: ['todo']
  }
</script>

<style scoped>
div.done {
  text-decoration: line-through;
  color: #b0b0b0;
}
</style>