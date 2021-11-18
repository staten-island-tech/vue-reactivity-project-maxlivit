<template>
  <div id="app">
    <div class="nav-bar">
       <img class = "logo" alt="Vue logo" src="./assets/livitlogo.png">
       <div class="nav-buttons">
         <button @click="poop(item)" v-for="item in clothing" :key="item">{{item}}</button>
         </div>

      </div> 
   <div class="show-img" v-for="item in clothing" :key="item" v-if="item=currentItem">
     
     </div>
  <div class="add"> 
    </div> 
  </div>
</template>

<script>
  export default {
    data() {
      return {
        currentItem: "",
        clothing: [
          "hats", 
          "shirts", 
          "hoodies", 
          "pants", 
          "shorts", 
          "socks", 
          "shoes",
        ],
        hats: [
          {
            name: "Yellow Hat",
            url: require("@/assets/yellowhat.png")
          },
        ], 
        shirts: [
          {
            name: "Yellow Shirt", 
            url: require("@/assets/yellowshirt.png")
          }
        ],
        hoodies: [
          {
            name: "Yellow Shirt", 
            url: require("@/assets/yellowhoodie.png")
          }
        ],
        pants: [
          {
            name: "Yellow Shirt", 
            url: require("@/assets/yellowpants.png")
          }
        ],
        shorts: [
          {
            name: "Yellow Shirt", 
            url: require("@/assets/yellowshorts.png")
          }
        ],
        socks: [
          {
            name: "Yellow Shirt", 
            url: require("@/assets/yellowsocks.png")
          }
        ],
        shoes: [
          {
            name: "Yellow Shirt", 
            url: require("@/assets/yellowshoes.png")
          }
        ],
      }
    }, 
    methods: {
      poop(item) {
        this.currentItem = item
      }
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
