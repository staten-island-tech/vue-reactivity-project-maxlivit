<template>

  <div id="app">
    <div class="nav-bar">
      <div class="logo-container">
       <img class="logo-img" alt="Vue logo" src="./assets/livitlogo.png">
       <h1 class="logo-text">Livit<span>DRESSER</span></h1>
      </div>
      <div class="inner-nav">
       <div class="nav-buttons">
         <button @click="
          home = 1,
          showHats = false, 
          showShirts = false,
          showHoodies = false, 
          showPants = false,
          showShorts = false,
          showSocks = false, 
          showShoes = false"
          class="button"><span>Home</span></button>
          <button @click="
          home = 0,
          showHats = false, 
          showShirts = false,
          showHoodies = false, 
          showPants = false,
          showShorts = false,
          showSocks = false, 
          showShoes = false"
          class="button"><span>Cart</span></button>
         <button @click="
          home = 0,
          showHats = true, 
          showShirts = false,
          showHoodies = false, 
          showPants = false,
          showShorts = false,
          showSocks = false, 
          showShoes = false"
          class="button"
          ><span>Hats</span></button>
         <button @click="
         home = 0,
         showHats = false, 
          showShirts = true,
          showHoodies = false, 
          showPants = false,
          showShorts = false,
          showSocks = false, 
          showShoes = false"
          class="button"><span>Shirts</span></button>
         <button @click="
         home = 0,
         showHats = false, 
          showShirts = false,
          showHoodies = true, 
          showPants = false,
          showShorts = false,
          showSocks = false, 
          showShoes = false"
          class="button"><span>Hoodies</span></button>
         <button @click="
         home = 0,
         showHats = false, 
          showShirts = false,
          showHoodies = false, 
          showPants = true,
          showShorts = false,
          showSocks = false, 
          showShoes = false"
          class="button"><span>Pants</span></button>
         <button @click="
         home = 0,
         showHats = false, 
          showShirts = false,
          showHoodies = false, 
          showPants = false,
          showShorts = true,
          showSocks = false, 
          showShoes = false"
          class="button"><span>Shorts</span></button>
         <button @click="
         home = 0,
         showHats = false, 
          showShirts = false,
          showHoodies = false, 
          showPants = false,
          showShorts = false,
          showSocks = true, 
          showShoes = false"
          class="button"><span>Socks</span></button>
         <button @click="
         home = 0,
         showHats = false, 
          showShirts = false,
          showHoodies = false, 
          showPants = false,
          showShorts = false,
          showSocks = false, 
          showShoes = true"
          class="button"><span>Shoes</span></button>
         </div>

      </div> 
      <div v-if="home > 0" id="home-screen">
       <h1 v-if="home > 0" class="welcome">Shop Your Style!</h1>
       <!-- <img :src="image"> -->
      <div id=slideset2 v-if="home > 0">
  <div>
    <h1>This is slide 1</h1>
    <p>Slide 1<img src="./assets/formalfit.png" class="formal"></p>
  </div>
  <div>
    <h1>This is the second slide</h1>
    <p>Second slide<img src="./assets/nikefit.png" class="nike"></p>
  </div>
  <div>
    <h1>This is slide number 3</h1>
    <p>Slide number 3</p>
  </div>
</div>
 <div class="cart">
    <p v-if="cart > 0">cart({{cart}})</p>
    <p v-else>Nothing in Cart</p>
    </div>
    </div>

      <section class='hat-section' v-if="showHats"> 
        <div class="show-hats" v-for="hat in hats" :key="hat" >
     <h1>{{hat.name}}</h1>
     <img :src="hat.url" class="hat-img">
     <button @click="addToCart">Add to Cart</button>
     <button @click="removeFromCart">Remove From Cart</button>
     </div>
        </section> 
   <section class='shirt-section' v-if="showShirts"> 
     <div class="show-shirts" v-for="shirt in shirts" :key="shirt">
     <h1>{{shirt.name}}</h1>
     <img :src="shirt.url" class="shirt-img">
     <button @click="addToCart">Add to Cart</button>
     <button @click="removeFromCart">Remove From Cart</button>
     </div>
      </section>
      <section class='hoodie-section' v-if="showHoodies"> 
     <div class="show-hoodies" v-for="hoodie in hoodies" :key="hoodie">
     <h1>{{hoodie.name}}</h1>
     <img :src="hoodie.url" class="hoodie-img">
      <button @click="addToCart">Add to Cart</button>
      <button @click="removeFromCart">Remove From Cart</button>
     </div>
     </section>
     <section class='pants-section' v-if="showPants"> 
     <div class="show-pants" v-for="pant in pants" :key="pant">
     <h1>{{pant.name}}</h1>
     <img :src="pant.url" class="pant-img">
      <button @click="addToCart">Add to Cart</button>
      <button @click="removeFromCart">Remove From Cart</button>
     </div>
     </section>
     <section class='shorts-section' v-if="showShorts"> 
     <div class="show-shorts" v-for="short in shorts" :key="short">
     <h1>{{short.name}}</h1>
     <img :src="short.url" class="short-img">
      <button @click="addToCart">Add to Cart</button>
      <button @click="removeFromCart">Remove From Cart</button>
     </div>
     </section>
     <section class='sock-section' v-if="showSocks"> 
     <div class="show-socks" v-for="sock in socks" :key="sock">
     <h1>{{sock.name}}</h1>
     <img :src="sock.url" class="sock-img">
      <button @click="addToCart">Add to Cart</button>
      <button @click="removeFromCart">Remove From Cart</button>
     </div>
     </section>
     <section class='shoe-section' v-if="showShoes"> 
     <div class="show-shoes" v-for="shoe in shoes" :key="shoe">
     <h1>{{shoe.name}}</h1>
     <img :src="shoe.url" class="shoe-img"> 
      <button @click="addToCart">Add to Cart</button>
      <button @click="removeFromCart">Remove From Cart</button>
     </div>
     </section>
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
        // image: require("@/assets/formalfit.png",
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
          name: "Yellow Nike  Hat",
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
          {
            name: "Hawaii Shorts", 
            category: "shorts",
            url: require("@/assets/hawaiishorts.png")
          },
          {
            name: "Supreme x NBA Shorts", 
            category: "shorts",
            url: require("@/assets/supremexnbashorts.png")
          },
          {
            name: "Nike UNC Basketball Shorts", 
            category: "shorts",
            url: require("@/assets/nikeuncshorts.png")
          },
          ],
          socks: [
          {
            name: "Golf Socks", 
            category: "socks",
            url: require("@/assets/golfsocks.png")
          },
          {
            name: "Nike Dri-Fit Socks", 
            category: "socks",
            url: require("@/assets/nikesocks.png")
          },
          {
            name: "Toe Socks", 
            category: "socks",
            url: require("@/assets/toesocks.png")
          },
          {
            name: "Watermelon Socks", 
            category: "socks",
            url: require("@/assets/watermelonsocks.png")
          },
          ],
          shoes: [
          {
            name: "Pink Fuzzy Slippers", 
            category: "shoes",
            url: require("@/assets/fuzzyslippers.png")
          },
          {
            name: "Black Leather Dress Shoes", 
            category: "shoes",
            url: require("@/assets/dressshoes.png")
          },
          {
            name: "Among Us Crocs", 
            category: "shoes",
            url: require("@/assets/amonguscrocs.png")
          },
          {
            name: "Rain Boots", 
            category: "shoes",
            url: require("@/assets/rainboots.png")
          },
          ],
        cart: 0, 
        home: 1,
      }
    }, 
    methods: {
        addToCart () {
          this.cart += 1
        },
        removeFromCart () {
          this.cart -=1
        }
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

.logo-img {
  width: 13rem;
  height: 10rem;
}

.logo-container {
  height: 100%;
  display: table;
  float: left;
  margin: 0 auto;
}

.logo-container h1 {
  color: black;
  height: 100%;
  display: table-cell;
  vertical-align: middle;
  font-size: 32px;
  font-weight: 200;
  float: right;
  margin: 3rem;
  margin-left: 1rem;
}

.logo-container h1 span {
  font-weight: 800;
}

.nav-bar {
  background-color: white;
  width: 100%;
  height: 120px;
  display: block;
  margin: 0 auto;
}

.inner-nav {
  width: 820px;
  height: 100%;
  display: inline-block;
  margin: 1rem;
  position: relative;
  background-color: white;
  margin-left: auto;
  margin-top: 3px;
  margin-right: auto;
}

.welcome {
  color: white;
  width: 85rem;
  text-align: center;
}

.nav-buttons {
    padding: 2rem;
    width: 60rem;
    margin-right: 20rem;
    height: 100%;
    margin: 0 auto;
    display: block;
}

.nav-buttons button:hover {
  background-color: lightgrey;
  color: black;
   box-shadow: 0 22px 26px 0 rgba(0,0,0,0.24), 0 17px 50px 0 rgba(0,0,0,0.19);
}

.nav-buttons button {
        transition-duration: .5s;
  margin: 1rem;
  background-color: white;
  color: black;
  border: none;
  border-radius: 10px;
  font-size: 20px;
}

.nav-buttons button:active {
  transform: translateY(15px);
}
.button span {
  cursor: pointer;
  display: inline-block;
  position: relative;
  transition: 0.2s;
}

.button span:after {
  content: '\00bb';
  position: absolute;
  opacity: 0;
  top: 0;
  right: -20px;
  transition: 0.2s;
}

.button:hover span {
  padding-right: 25px;
}

.button:hover span:after {
  opacity: 1;
  right: 0;
}

.app {
  display: flex;
}

#home-screen {
    background-image: url("./assets/background.jpg");
    background-size: 90rem;
    position: relative;
}

#slideset2 {
  height: 49rem; 
  position: relative;
  overflow: hidden;
  display: flex;
  justify-content: center;
  }

#slideset2 > * {position: absolute; top: 100%; left: 0;
  animation: 12s autoplay2 infinite ease-in-out}

  @keyframes autoplay2 {
  0% {top: 100%}
  4% {top: 0%}
  33.33% {top: 0%}
  37.33% {top: -100%}
  100% {top: -100%}
}

#slideset2 > *:nth-child(1) {animation-delay: 0s}
#slideset2 > *:nth-child(2) {animation-delay: 4s}
#slideset2 > *:nth-child(3) {animation-delay: 8s}

.formal {
  height: 40rem;
  width: 20rem;
}
.nike {
  height: 35rem;
  width: 35rem;
}

</style>
