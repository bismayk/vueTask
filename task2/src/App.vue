<template>
  <div id="app">
    <StateDetails/>
    <br><br><br><br><br><br>
    <Sorting/>
  </div>
</template>

<script>
import StateDetails from './components/StateDetails'
import Sorting from './components/Sorting'

export default {
  name: 'App',
  components: {
    StateDetails,
    Sorting
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  margin-top: 60px;
}
</style>
