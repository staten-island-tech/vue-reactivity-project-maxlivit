<template>
  <div id="app">
    <div class="nav-bar">
       <img class = "logo" alt="Vue logo" src="./assets/livitlogo.png">
       <div class="nav-buttons">
         <button @click="chosen(item)" v-for="item in clothingNames" :key="item">{{item}}</button>
         </div>

      </div> 
   <div class="show-img" v-for="item in clothing" :key="item">
     <h1>{{item.category}}</h1>
     <img :src="item.url">
     </div>
  <div class="add"> 
    </div> 
  <div class="cart">
    <p>cart({{cart}})</p>
    </div>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        currentItem: "",
        clothingNames: [
          "hats", 
          "shirts", 
          "hoodies", 
          "pants", 
          "shorts", 
          "socks", 
          "shoes",
        ],
        clothing: [
          {
            name: "Yellow Hat",
            category: "hat",
            url: require("@/assets/yellowhat.png")
          },
         { name:"Blue Hat",
          category: "hat",
          url: require("@/assets/bluehat.png")
         },
          {
            name: "Yellow Shirt", 
            category: "shirts",
            url: require("@/assets/yellowshirt.png")
          },
          {
            name: "Yellow Hoodie", 
            category: "hoodies",
            url: require("@/assets/yellowhoodie.png")
          },
          {
            name: "Yellow Pants", 
            category: "pants",
            url: require("@/assets/yellowpants.png")
          },
          {
            name: "Yellow Shorts", 
            category: "shorts",
            url: require("@/assets/yellowshorts.png")
          },
          {
            name: "Yellow Socks", 
            category: "socks",
            url: require("@/assets/yellowsocks.png")
          },
          {
            name: "Yellow Shoes", 
            category: "shoes",
            url: require("@/assets/yellowshoes.png")
          },
        ],
        cart: 0
      }
    }, 
    methods: {
      chosen(item) {
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
