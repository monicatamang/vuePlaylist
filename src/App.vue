<template>
  <div id="app">
    <page-body></page-body>
  </div>
</template>

<script>

// Importing the body component into the home page
import PageBody from "./components/PageBody.vue";

// Registering the body component
export default {
  name: 'App',
  components: {
    PageBody,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: 60px 0px;
}
</style>
