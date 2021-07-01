<template>
  <h1>Todo-List Vue</h1>
  <TodoInput @add-item="addItem" />
  <TodoItem @remove-item="removeItem" :List="List" />
</template>

<script>
import TodoInput from "./components/TodoInput.vue";
import TodoItem from "./components/TodoItem.vue";

export default {
  name: "App",
  components: {
    TodoInput,
    TodoItem,
  },
  data() {
    return {
      List: [],
    };
  },
  methods: {
    addItem(item) {
      if (item) {
        this.List.push(item);
      }
    },
    removeItem(item) {
      this.List = this.List.filter((currentValue) => currentValue != item);
    },
  },
};
</script>

<style>
*:focus {
  outline: none;
}

body {
  background-color: rgb(110, 55, 212);
  display: grid;
  place-items: center;
}

#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background-color: white;
  box-shadow: 0 2px 3px rgb(87, 87, 87);
  color: #2c3e50;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  font-weight: bold;
  margin-top: 60px;
  padding: 20px;
  text-align: center;
  min-width: 300px;
}
</style>
