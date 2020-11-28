<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <Form msg="Winnard" v-on:add="addValue" />
  <Todos
    v-bind:todos="todos"
    v-on:completed="markComplete"
    v-on:del-todo="deleteTodo"
  />
</template>

<script>
//import HelloWorld from "./components/HelloWorld.vue";
import Form from "./components/Form.vue";
import Todos from "./components/Todos.vue";

export default {
  name: "App",
  components: {
    Form,
    Todos,
  },
  methods: {
    addValue(newValue) {
      // const {desc,completed} = newValue
      this.todos = [...this.todos, newValue];
      console.log(this.todos);
    },

    markComplete(id) {
      //alert("dsf".id);
      // this.todos = this.todos.filter((todo) => todo.id !== id);

      const todo = this.todos.find((obj) => obj.id === id);
      todo.completed = !todo.completed;
      //this.todo.completed = !this.todo.completed;
    },

    deleteTodo(id) {
      this.todos = this.todos.filter((todo) => todo.id !== id);
    },
  },

  data() {
    return {
      todos: [
        {
          id: 1,
          desc: "hello1",
          completed: true,
        },
        {
          id: 2,
          desc: "hello2",
          completed: false,
        },
        {
          id: 3,
          desc: "hello3",
          completed: false,
        },
      ],
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
