<template>
  <div id="app">
    <Header/>
    <Calc/>
  </div>
</template>

<script>
import Calc from './components/Calc'
import Header from './components/Header'

export default {
  name: 'App',
  components: {
    Calc,
    Header
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin-top: 60px;
}
</style>
