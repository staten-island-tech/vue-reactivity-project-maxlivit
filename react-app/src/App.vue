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
       <div class="cart">
    <p>cart({{cart}})</p>
    </div>
      <section class='hat-section' v-if="showHats"> 
        <div class="show-hats" v-for="hat in hats" :key="hat" >
     <h1>{{hat.name}}</h1>
     <img :src="hat.url" class="hat-img">
     <button @click="addToCart">Add to Cart</button>
     </div>
        </section> 
   <section class='shirt-section' v-if="showShirts"> 
     <div class="show-shirts" v-for="shirt in shirts" :key="shirt">
     <h1>{{shirt.name}}</h1>
     <img :src="shirt.url" class="shirt-img">
     <button @click="addToCart">Add to Cart</button>
     </div>
      </section>
      <section class='hoodie-section' v-if="showHoodies"> 
     <div class="show-hoodies" v-for="hoodie in hoodies" :key="hoodie">
     <h1>{{hoodie.name}}</h1>
     <img :src="hoodie.url" class="hoodie-img">
     </div>
     </section>
     <section class='pants-section' v-if="showPants"> 
     <div class="show-pants" v-for="pant in pants" :key="pant">
     <h1>{{pant.name}}</h1>
     <img :src="pant.url" class="pant-img">
     </div>
     </section>
     <section class='shorts-section' v-if="showShorts"> 
     <div class="show-shorts" v-for="short in shorts" :key="short">
     <h1>{{short.name}}</h1>
     <img :src="short.url" class="short-img">
     </div>
     </section>
     <section class='sock-section' v-if="showSocks"> 
     <div class="show-socks" v-for="sock in socks" :key="sock">
     <h1>{{sock.name}}</h1>
     <img :src="sock.url" class="sock-img">
     </div>
     </section>
     <section class='shoe-section' v-if="showShoes"> 
     <div class="show-shoes" v-for="shoe in shoes" :key="shoe">
     <h1>{{shoe.name}}</h1>
     <img :src="shoe.url" class="shoe-img"> 
     </div>
     </section>
  <div class="add"> 
    </div> 
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
            {
              name:"New York Rangers Hat",
              category: "hats",
              url: require("@/assets/nyrhat.png")
            },
             {
              name:"Stay Cool Hat",
              category: "hats",
              url: require("@/assets/staycoolhat.png")
            },
            ],
          shirts: [
          {
            name: "Yellow Shirt", 
            category: "shirts",
            url: require("@/assets/yellowshirt.png")
          },
          {
            name: "Code Shirt", 
            category: "shirts",
            url: require("@/assets/codeshirt.png")
          },
          {
            name: "I Hate You & You Look Like A Fish Shirt", 
            category: "shirts",
            url: require("@/assets/fishshirt.png")
          },
          {
            name: "Supreme Shirt", 
            category: "shirts",
            url: require("@/assets/supremeshirt.png")
          },
          ],
          hoodies: [
          {
            name: "Lil Durk OTF Hoodie", 
            category: "hoodies",
            url: require("@/assets/lildurkhoodie.png")
          },
           {
            name: "Dragon Blossom Hoodie", 
            category: "hoodies",
            url: require("@/assets/dragonhoodie.png")
          },
           {
            name: "Juice Wrld 999 Hoodie", 
            category: "hoodies",
            url: require("@/assets/juicewrldhoodie.png")
          },
           {
            name: "Custom Red Hoodie", 
            category: "hoodies",
            url: require("@/assets/customredhoodie.png")
          },
          ],
          pants: [
          {
            name: "Grey Joggers", 
            category: "pants",
            url: require("@/assets/greyjoggers.png")
          },
          {
            name: "Rick & Morty Neon Portal Joggers", 
            category: "pants",
            url: require("@/assets/neonportaljoggers.png")
          },
          {
            name: "Dark Denim Jeans", 
            category: "pants",
            url: require("@/assets/darkdenimjeans.png")
          },
          {
            name: "Moon Joggers", 
            category: "pants",
            url: require("@/assets/moonjoggers.png")
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
.hat-img {
  width: 25rem;
  height: 25rem;
}
.shirt-img {
  width: 25rem;
  height: 25rem;
}
.hoodie-img {
  width: 25rem;
  height: 25rem;
}
.pant-img {
  width: 25rem;
  height: 25rem;
}
.short-img {
  width: 25rem;
  height: 25rem;
}
.sock-img {
  width: 25rem;
  height: 25rem;
}
.shoe-img {
  width: 25rem;
  height: 25rem;
}


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
