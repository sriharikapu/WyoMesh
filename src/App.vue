<template>
  <div id="app">
    <md-toolbar class="md-primary">
      <h1>WyoMesh Auditing Frontend</h1>
    </md-toolbar>
    <WyoMesh/>
  </div>
</template>

<script>
import WyoMesh from './components/WyoMesh.vue'

export default {
  name: 'app',
  components: {
    WyoMesh
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
