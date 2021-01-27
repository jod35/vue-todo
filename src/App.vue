<template>
  <div id="app">
    <center>
        <h1>Todo App</h1>
        <Main/>
    </center>
  </div>
</template>

<script>

import Main from './components/Main.vue'
export default {
  name: 'App',
  components: {
    Main
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
  margin-top: 60px;
}
</style>
