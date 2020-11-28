
<template>
  <div>
    <div v-bind:key="todo" v-for="todo in todos">
      <TodoItem
        v-bind:todo="todo"
        todo.sync="todo"
        v-on:completed="$emit('completed', todo.id)"
        v-on:del-todo="$emit('del-todo', todo.id)"
      />
      <!--<TodoItem v-for="todo in todos" :key="todo.id" todo_prop.sync="todo" />-->
    </div>
  </div>
</template>

<script>
import TodoItem from "./TodoItem";

export default {
  name: "Todos",
  components: {
    TodoItem,
  },
  props: ["todos"],
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
