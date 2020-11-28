<template>
  <div class="todo-item" v-bind:class="{ 'is-completed': todo.completed }">
    <label>
      <input
        type="checkbox"
        @change="$emit('completed', todo.id)"
        v-bind:checked="todo.completed"
      />

      {{ todo.desc }}

      <button @click="$emit('del-todo', todo.id)" class="del">x</button>
    </label>
  </div>
</template>
    
    <script>
export default {
  name: "TodoItem",
  props: ["todo"],

  methods: {
    markCompleted() {
      //this.todo.completed = !this.todo.completed;
      console.log(this.todo);
      this.$emit("completed", true);
    },
  },
};
</script>


<style scoped>
.is-completed {
  color: red;
  text-decoration: line-through;
}
label {
  cursor: pointer;
}
.del {
  background: #ff0000;
  color: #fff;
  border: none;
  border-radius: 50%;
  cursor: pointer;
}
</style>