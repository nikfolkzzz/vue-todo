<template>
  <div class="todo-list">
    <ul v-for="(t,index) in todos" :key="t.id">
      <TodoItem :todo="t" :index="index" @remove-todo="removeTodo" />
    </ul>
  </div>
</template>



<script>
import TodoItem from "./TodoItem";
export default {
  props: {
    todos: Array,
  },

  components: {
    TodoItem,
  },

  methods: {
    removeTodo(id) {
      this.$emit("remove-todo", id);
    },
  },
};
</script>


<style scoped>
ul {
  list-style-type: none;
  display: flex;
  margin: 0;
  padding: 0;
  margin-bottom: 1rem;
}
</style>