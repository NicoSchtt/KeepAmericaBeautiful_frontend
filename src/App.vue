<template>
  <div id="app">
    <Header />
    <MapContent />
  </div>
</template>

<script>
import Header from "./components/header/Header";
import MapContent from "./components/content/MapContent";

export default {
  name: 'App',
  components: {
    MapContent,
    Header,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-left: 20px;
  margin-right: 20px;
}
</style>
