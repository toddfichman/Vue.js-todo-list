<template>
  <div>
    <div v-bind:key="todo.id" v-for="todo in todos"> <!-- v-for is how you loop through array with vue, also need to bind a uniq key -->
      <TodoItem v-bind:todo="todo" v-on:del-todo="$emit('del-todo', todo.id)"/> <!-- passing up del-todo from TodoItem up to App, with todo.id as parameter -->
    </div>
  </div>
</template>

<script>
import TodoItem from './TodoItem.vue'

export default {
  name: 'Todos',
  components: {
    TodoItem
  },
  props: ['todos'] //getting props from App.vue from v-bind
}
</script>


<style scoped>

</style>
