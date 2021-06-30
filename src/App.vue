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
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
