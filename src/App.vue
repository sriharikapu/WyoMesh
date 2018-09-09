<template>
  <div id="app">
    <md-toolbar class="md-primary">
      <h1>WyoMesh Audit</h1>
    </md-toolbar>
    <IndeedScraperExport/>
  </div>
</template>

<script>
import IndeedScraperExport from './components/IndeedScraperExport.vue'

export default {
  name: 'app',
  components: {
    IndeedScraperExport
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
}
</style>
