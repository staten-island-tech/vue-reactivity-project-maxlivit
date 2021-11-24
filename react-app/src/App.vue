<template>
  <div id="app">
    <div class="nav-bar">
       <img class = "logo" alt="Vue logo" src="./assets/livitlogo.png">
       <div class="nav-buttons">
         <button @click="
          showHats = true, 
          showShirts = false,
          showHoodies = false, 
          showPants = false,
          showShorts = false,
          showSocks = false, 
          showShoes = false"
          >Hats</button>
         <button @click="showHats = false, 
          showShirts = true,
          showHoodies = false, 
          showPants = false,
          showShorts = false,
          showSocks = false, 
          showShoes = false">Shirts</button>
         <button @click="showHats = false, 
          showShirts = false,
          showHoodies = true, 
          showPants = false,
          showShorts = false,
          showSocks = false, 
          showShoes = false">Hoodies</button>
         <button @click="showHats = false, 
          showShirts = false,
          showHoodies = false, 
          showPants = true,
          showShorts = false,
          showSocks = false, 
          showShoes = false">Pants</button>
         <button @click="showHats = false, 
          showShirts = false,
          showHoodies = false, 
          showPants = false,
          showShorts = true,
          showSocks = false, 
          showShoes = false">Shorts</button>
         <button @click="showHats = false, 
          showShirts = false,
          showHoodies = false, 
          showPants = false,
          showShorts = false,
          showSocks = true, 
          showShoes = false">Socks</button>
         <button @click="showHats = false, 
          showShirts = false,
          showHoodies = false, 
          showPants = false,
          showShorts = false,
          showSocks = false, 
          showShoes = true">Shoes</button>
         </div>

      </div> 
      <section class='hat-section' v-if="showHats"> 
        <div class="show-hats" v-for="hat in hats" :key="hat" >
     <h1>{{hat.name}}</h1>
     <img :src="hat.url">
     </div>
        </section> 
   <section class='shirt-section' v-if="showShirts"> 
     <div class="show-shirts" v-for="shirt in shirts" :key="shirt">
     <h1>{{shirt.name}}</h1>
     <img :src="shirt.url">
     </div>
      </section>
      <section class='hoodie-section' v-if="showHoodies"> 
     <div class="show-hoodies" v-for="hoodie in hoodies" :key="hoodie">
     <h1>{{hoodie.name}}</h1>
     <img :src="hoodie.url">
     </div>
     </section>
     <section class='pants-section' v-if="showPants"> 
     <div class="show-pants" v-for="pant in pants" :key="pant">
     <h1>{{pant.name}}</h1>
     <img :src="pant.url">
     </div>
     </section>
     <section class='shorts-section' v-if="showShorts"> 
     <div class="show-shorts" v-for="short in shorts" :key="short">
     <h1>{{short.name}}</h1>
     <img :src="short.url">
     </div>
     </section>
     <section class='sock-section' v-if="showSocks"> 
     <div class="show-socks" v-for="sock in socks" :key="sock">
     <h1>{{sock.name}}</h1>
     <img :src="sock.url">
     </div>
     </section>
     <section class='shoe-section' v-if="showShoes"> 
     <div class="show-shoes" v-for="shoe in shoes" :key="shoe">
     <h1>{{shoe.name}}</h1>
     <img :src="shoe.url">
     </div>
     </section>
  <div class="add"> 
    </div> 
  <div class="cart">
    <p>cart({{cart}})</p>
    </div>
    <product :premium="premium" @add-to-cart="updateCart"></product>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        showHats: false,
        showShirts: false,
        showHoodies: false,
        showPants: false,
        showShorts: false,
        showSocks: false,
        showShoes: false,
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
        hats: [
          { 
          name: "Yellow Hat",
            category: "hats",
            url: require("@/assets/yellowhat.png")
            },
            {
              name:"Blue Hat",
          category: "hats",
          url: require("@/assets/bluehat.png")
            },
            ],
          shirts: [
          {
            name: "Yellow Shirt", 
            category: "shirts",
            url: require("@/assets/yellowshirt.png")
          },
          ],
          hoodies: [
          {
            name: "Yellow Hoodie", 
            category: "hoodies",
            url: require("@/assets/yellowhoodie.png")
          },
          ],
          pants: [
          {
            name: "Yellow Pants", 
            category: "pants",
            url: require("@/assets/yellowpants.png")
          },
          ],
          shorts: [
          {
            name: "Yellow Shorts", 
            category: "shorts",
            url: require("@/assets/yellowshorts.png")
          },
          ],
          socks: [
          {
            name: "Yellow Socks", 
            category: "socks",
            url: require("@/assets/yellowsocks.png")
          },
          ],
          shoes: [
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
        addToCart () {
          this.cart += 1
        },
      },
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
