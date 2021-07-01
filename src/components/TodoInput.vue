<template>
  <div>
    <input
      type="text"
      placeholder="Enter a task..."
      ref="Input"
      v-model="inputValue"
    />
    <button @click="add">+</button>
  </div>
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

<style scoped lang="scss">
div {
  display: grid;
  gap: 5px;
  grid-template-columns: auto 40px;
  height: 40px;

  input {
    padding: 8px 10px;
    font-weight: bold;
  }

  button {
    background-color: rgb(114, 61, 211);
    border: none;
    border-radius: 2px;
    box-shadow: 0 0 2px rgb(0, 0, 0);
    color: white;
    font-size: 25px;
    font-weight: bold;
    transition: transform 250ms;

    &:hover {
      transform: scale(1.1);
    }
  }
}
</style>