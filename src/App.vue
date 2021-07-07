<template>
  <div id="app">
    <CloneInput />
  </div>
</template>

<script>
import CloneInput from "./components/CloneInput";

export default {
  name: "App",
  components: {
    CloneInput,
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
