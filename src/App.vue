<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <ComponentDemo />
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import ComponentDemo from "./components/ComponentDemo/index";

export default {
  name: "App",
  components: {
    // HelloWorld
    ComponentDemo
  }
};
</script>

<style>
/* #app {
  font-family: Avenir, Helv etica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;

  margin-top: 60px;
} */
</style>
