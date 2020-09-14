<template>
  <div id="app">
    <div class="container">
      <h1>todo app</h1>
      <AddTodo @add-todo="addTodo" />
      <TodoList @remove-todo="removeTodo" :todos="todos" />
    </div>
  </div>
</template>

<script>
import TodoList from "./components/TodoList";
import AddTodo from "./components/AddTodo";
export default {
  name: "App",
  components: {
    TodoList,
    AddTodo,
  },
  methods: {
    removeTodo(id) {
      this.todos = this.todos.filter((item) => item.id !== id);
    },

    addTodo(title) {
      const task = {
        id: Date.now(),
        title: title,
        complete: false,
      };

      if (task.title !== "") this.todos.push(task);
    },
  },

  data() {
    return {
      todos: [
        {
          id: 1,
          title: "ceasar",
          complete: false,
        },
        {
          id: 2,
          title: "napoleon",
          complete: false,
        },
        {
          id: 3,
          title: "alexander",
          complete: false,
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

.container {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
