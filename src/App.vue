<script>
// import HelloWorld from "./components/HelloWorld.vue";
import Header from "./components/Header.vue";
import Content from "./components/Content.vue";
import { defineComponent, ref } from "vue";

export default {
  components: {
    Header,
    Content,
  },

  setup() {},
};
</script>

<template>
  <div class="wrapper">
    <Header></Header>
    <Content />
  </div>
</template>

<style>
*,
*::after,
*::before {
  margin: 0px;
  padding: 0px;
  box-sizing: border-box;
}
body {
  max-width: 1400px;
  margin: 0 auto;
}
.wrapper {
  width: 100%;
  margin: 0 auto;
  padding: 0px 20px;
  background-color: aliceblue;
}
</style>
