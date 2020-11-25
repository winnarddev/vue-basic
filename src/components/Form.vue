
<template>
  <div>
    <h3>Hello {{ msg }}</h3>

    <form @submit="add">
      <input type="text" v-model="desc" name="desc" />
      <input type="submit" />
    </form>
  </div>
</template>

<script>
export default {
  name: "Form",
  props: {
    msg: String,
  },
  data() {},
  methods: {
    add(e) {
      e.preventDefault();
      const newValue = {
        id: 4,
        desc: this.desc,
        completed: false,
      };
      this.$emit("add", newValue);
    },
  },
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
