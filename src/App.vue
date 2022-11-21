<template>
  <div id="app">
    <Header mainTitle="Pokélist" />
    <List />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import List from "./components/List.vue";

export default {
  name: "App",
  components: {
    Header,
    List
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

.translucide {
  transition: background-color 0.5s cubic-bezier(0.28, 0.11, 0.32, 1);
  backdrop-filter: blur(10px);
  background-color: rgba(255, 255, 255, 0.6);
}
</style>
