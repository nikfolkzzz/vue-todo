<template>
  <li>
    <span :class="{done:todo.complete}">
      <input type="checkbox" v-model="todo.complete" />
      {{index+1}}
      {{todo.title}}
    </span>

    <button @click="$emit('remove-todo',todo.id)">X</button>
  </li>
</template>



<script>
export default {
  props: {
    todo: Object,
    index: Number,
  },
};
</script>


<style  scoped>
li {
  border: 1px solid #000;
  width: 500px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
span {
  padding: 0.5rem;
}

.done {
  text-decoration: line-through;
}

button {
  margin: 0.5rem;
  background-color: red;
  border-radius: 50%;
  width: 20px;
  height: 20px;
  color: white;
  border: none;
}
</style>