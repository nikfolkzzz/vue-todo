<template>
  <form action class="form-add" @submit.prevent="onSubmit">
    <input type="text" v-model="title" />
    <button type="submit">add todo</button>
  </form>
</template>



<script>
export default {
  data() {
    return {
      title: "",
    };
  },

  methods: {
    onSubmit() {
      this.$emit("add-todo", this.title);
      this.title = "";
    },
  },
};
</script>



<style scoped>
.form-add {
  margin-bottom: 1rem;
}

button {
  background-color: lightgreen;
}
</style>