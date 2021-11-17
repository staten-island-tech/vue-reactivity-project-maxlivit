<template>
  <div id="app">
    <div class="nav-bar">
       <img class = "logo" alt="Vue logo" src="./assets/livitlogo.png">
       <div class="nav-buttons">
         <button>hats</button>
         <button>shirts</button>
         <button>hoodies</button>
         <button>pants</button>
         <button>shorts</button>
         <button>shoes</button>
         <button>socks</button>
         </div>

      </div> 
   <div class="selecting">

     </div>
  <div class="add"> 
    </div> 
  </div>
</template>

<script>
  export default {
    data() {
      return {
        x: 0,
        hats: [
          {
            name: "Yellow Hat"
           // url: require()
          },
        ], 
        shirts: [

        ],
      }
    }, 
    methods: {
      updateHat(index) {
        this.selectedHat = index
      },

    }, 
    computed: {
      hatImage() {
        return this.hats[this.selectedHat].url;
      },
    }
  }

</script>

<style lang="scss">
.logo {
  width: 11rem;
  height: 8rem;
}

.nav-bar {
  background-color: lightblue;
  width: 100%;
  height: fit-content;
  display: flex;
  justify-content: space-between;
}

.nav-buttons {
    margin-right: 50%;
}

.nav-buttons button {
  margin: 2rem;
}
</style>
