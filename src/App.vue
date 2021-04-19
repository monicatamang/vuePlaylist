<template>
  <div id="app">
    <page-body></page-body>

    <!-- Added fonts -->
    <link rel="preconnect" href="https://fonts.gstatic.com">
    <link href="https://fonts.googleapis.com/css2?family=Rubik:wght@300;400&display=swap" rel="stylesheet">
  </div>
</template>

<script>
// Importing the body component into the home page
import PageBody from "./components/PageBody.vue";

// Registering the body component
export default {
  name: 'App',
  components: {
    PageBody
  }
}
</script>

<style>
#app {
  font-family: 'Rubik', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  background: #222222;
  color: white;
}

* {
  margin: 0;
  padding: 0;
}
</style>