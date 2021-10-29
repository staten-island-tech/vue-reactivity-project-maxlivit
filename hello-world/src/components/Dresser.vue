<template>
  <div class="main">
      <header class="header">
         <h1 class="h1">Build Your Fit</h1>
      <img class = "logo" src = "../assets/livitlogo.png">
      </header>
      <img class="body-img" src="../assets/images/body.png">
      <img class="blonde" src="../assets/images/blonde2.png">
      <img class="brunette" src="../assets/images/brunette.png">
        <img class="shirt1" src="../assets/images/shirt1.png">
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

.body-img { 
  display: block;
  margin: auto;
}

.blonde {
  display:block;
  margin: auto;
  width: 4.1rem;
  height: 2.5rem;
  position: relative;
  top: -30.7rem;
  left: 2px;
}

.brunette {
    display:block;
  margin: auto;
  width: 6rem;
  height: 8.5rem;
  position: relative;
  top: -33.5rem;
  left: 7px;
}

.shirt1 {
    display:block;
  margin: auto;
  width: 12rem;
  height: 12rem;
  position: relative;
  top: -36.5rem;
  left: 2px;
}

</style>