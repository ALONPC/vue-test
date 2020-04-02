<template>
  <div id="app">
    <img class="logo" src="./assets/ameiz.svg" />
    <Gallery />
  </div>
</template>

<script>
import Gallery from "./components/Gallery.vue";

export default {
  name: "App",
  components: {
    Gallery
  }
};
</script>

<style>
.logo {
  height: 150px;
  width: 150px;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
