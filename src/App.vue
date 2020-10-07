<template>
  <div id="app">
    <Navbar />
    <Notes />
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue'
import Notes from './components/Notes.vue'

export default {
  name: 'App',
  components: {
    Navbar,
    Notes
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
