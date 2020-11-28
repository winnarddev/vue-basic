
<template>
  <div>
    <h3>Hello {{ msg }}</h3>

    <form @submit.prevent="add">
      <input type="text" v-model="desc" name="desc" placeholder="Add Todo..." />
      <input type="submit" /><br />
      <span class="errorMsg">{{ errorMsg }}</span>
    </form>
  </div>
</template>

<script>
export default {
  name: "Form",
  props: {
    msg: String,
  },
  data() {
    return { errorMsg: "", desc: "" };
  },
  methods: {
    add(e) {
      e.preventDefault();
      if (!this.desc) {
        this.errorMsg = "Please enter";
      } else {
        const newValue = {
          id: 4,
          desc: this.desc,
          completed: false,
        };
        this.$emit("add", newValue);
        this.desc = "";
        e.target.reset();
      }
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
.errorMsg {
  color: red;
}
</style>
