<template>
  <div id="app">
    <ProductDetails/>
    <br><br><br><br><br><br><br><br>
    <todos/>
  </div>
</template>

<script>
import ProductDetails from './components/ProductDetails'
import todos from './components/todos'

export default {
  name: 'App',
  components: {
    ProductDetails,
    todos
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
