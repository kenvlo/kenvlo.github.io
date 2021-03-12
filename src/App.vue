<template>
  <div id="app">
    <Portfolio />
  </div>
</template>

<script>
import Portfolio from "./components/Portfolio.vue";

export default {
  name: "App",
  components: {
    Portfolio,
  },
};
</script>

<style>
#app {
  font-family: Spartan, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
