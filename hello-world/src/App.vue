<template>
  <div id="app">
    <Dresser />
  </div>
</template>

<script>
import Dresser from "./components/Dresser.vue"
export default {
  name: 'App',
  components: {
    Dresser
  }
}
</script>


<style>
html,body {
  background: blanchedalmond;
  height: 100vh;
  margin: 0;
  padding: 0;
}
</style>
