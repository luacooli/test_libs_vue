<template>
  <div id="app">
    <Viewer />
    <D3Chart />
    <GoogleCharts />
  </div>
</template>

<script>
import GoogleCharts from './components/GoogleCharts.vue'
import D3Chart from './components/D3Chart.vue'
import Viewer from './components/Viewer.vue'

export default {
  name: 'App',
  components: {
    Viewer,
    D3Chart,
    GoogleCharts
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
