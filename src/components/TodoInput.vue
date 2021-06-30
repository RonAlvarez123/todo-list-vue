<template>
  <input type="text" ref="Input" v-model="inputValue" />
  <button @click="add">Add Item</button>
</template>

<script>
export default {
  name: "TodoInput",
  data() {
    return {
      itemValue: undefined,
    };
  },
  methods: {
    add() {
      this.$emit("addItem", this.inputValue);
      this.inputValue = undefined;
      this.$refs.Input.value = "";
      this.$refs.Input.focus();
    },
  },
};
</script>

<style>
li {
  display: grid;
  grid-template-columns: auto 80px;
  list-style-type: none;
}
</style>