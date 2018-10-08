<template>
  <div id="app">
    <PurchaseList/>
  </div>
</template>

<script>
import PurchaseList from './components/PurchaseList'

export default {
  name: 'App',
  components: {
    PurchaseList
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
