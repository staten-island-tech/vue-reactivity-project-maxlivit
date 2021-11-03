<template>
  <div class="main">
      <header class="header">
         <h1 class="h1">Build Your Fit</h1>
      <img class = "logo" src = "../assets/livitlogo.png">
      </header>
  </div>
</template>

<script>

export default {
  name: 'Dresser',
  data() {
      return {
          hair: [
            {
              name: "blonde",
              url: (""),
            },
            {
              name: "",
              url: (""),
            }
          ]
      }
  }, 
  methods: {

  },
  computed: {

  }
}

</script>

<style>
.main{
  background: blanchedalmond;
  height: 100vh;
  margin: 0;
  padding: 0;
}
.logo {
    width: 20rem;
    margin-top: -5rem;
}

.h1 {
    text-align: center;
    font-family: ;
}
.header {

}

</style>