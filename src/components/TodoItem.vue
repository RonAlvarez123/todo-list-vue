<template>
  <li v-for="lists in List" :key="lists">
    <p ref="listItem">{{ lists }}</p>
    <button @click="remove">Remove</button>
  </li>
</template>

<script>
export default {
  props: ["List"],
  methods: {
    remove(e) {
      this.$emit("removeItem", e.target.parentElement.childNodes[0].innerText);
    },
  },
};
</script>

<style>
</style>