<template>
  <li v-for="lists in List" :key="lists">
    <p ref="listItem">{{ lists }}</p>
    <button @click="remove">
      <img :src="imgPath" alt="" />
    </button>
  </li>
</template>

<script>
export default {
  props: ["List"],
  data() {
    return {
      imgPath: require("../assets/recycle-bin.svg"),
    };
  },
  methods: {
    remove(e) {
      let Element = null;
      if (e.target.parentElement.parentElement.childNodes[0].nodeName == "P") {
        Element = e.target.parentElement.parentElement.childNodes[0];
      } else if (e.target.parentElement.childNodes[0].nodeName == "P") {
        Element = e.target.parentElement.childNodes[0];
      }
      this.$emit("removeItem", Element.innerText);
    },
  },
};
</script>

<style scoped lang="scss">
li {
  display: grid;
  grid-template-columns: auto 40px;
  grid-template-rows: 40px;
  list-style-type: none;
  margin-bottom: 10px;

  &:first-of-type {
    margin-top: 10px;
  }

  & > * {
    margin: 0;
  }

  p {
    align-items: center;
    background-color: #ddd;
    color: blue;
    display: flex;
    text-align: left;
    text-indent: 10px;
  }

  button {
    background-color: rgb(223, 13, 13);
    border: none;

    img {
      filter: brightness(0) invert(1);
      height: 65%;
      width: 65%;
    }
  }
}
</style>