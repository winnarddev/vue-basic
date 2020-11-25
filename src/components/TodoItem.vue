<template>
  <div v-bind:class="{ 'is-completed': todo.completed }">
    <input type="checkbox" v-on:change="markComplete" />
    {{ todo.desc }}
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo"],
  methods: {
    markComplete() {
      //this.todo.completed = true;
      this.$emit("completed", true);
      console.log(this.todo);
    },
  },
};
</script>

<style scoped>
.is-completed {
  text-decoration: line-through;
  color: red;
}
</style>