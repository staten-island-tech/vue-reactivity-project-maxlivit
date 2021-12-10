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
          showCart = false,
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
          showCart = true,
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
          showCart = false,
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
         showCart = false,
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
         showCart = false,
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
         showCart = false,
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
         showCart = false,
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
         showCart = false,
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
         showCart = false,
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
          </div>
      <div v-if="home > 0" class="home-screen">
       <h1 v-if="home > 0" class="welcome">Shop Your Style!</h1>
       <!-- <img :src="image"> -->
      <div class=slideset2 v-if="home > 0">
      <div class="sliding-gallery">
        <div>
          <!-- <h1>This is slide 1</h1> -->
          <img src="./assets/formalfit.png" class="formal">
        </div>
        <div>
          <!-- <h1>This is the second slide</h1> -->
          <img src="./assets/ballplayer.png" class="nike">
        </div>
        <div>
          <!-- <h1>This is slide number 3</h1> -->
          <img src="./assets/chillfit.png" class="casual">
        </div>
      </div>
</div>
</div>
 
    <section class='category-section' v-if="showCart"> 
      <div class="cart">
        <h1 class="cart-heading">Your Cart</h1>
        <div class="cart-container" v-for="cartItem in cart" :key="cartItem">
        <img :src="cartItem.url" class="cart-img">
        <h1 class="cart-title">{{cartItem.name}}</h1>
      </div>
      <button class="check-button"><span>Check Out</span></button>
        </div>
    </section>
 
    <section class='category-section' v-if="showHats"> 
      <div class="product-container" v-for="(hat, index) in products.hats" :key="index">
        <h1 class="product-title">{{hat.name}}</h1>
        <img :src="hat.url" class="product-img">
        <button @click="addHatToCart(index)" class="cart-button">Add to Cart</button>
        </div>
    </section> 
 
    <section class='category-section' v-if="showShirts"> 
      <div class="product-container" v-for="(shirt, index) in products.shirts" :key="index">
        <h1 class="product-title">{{shirt.name}}</h1>
        <img :src="shirt.url" class="product-img">
        <button @click="addShirtToCart(index)" class="cart-button">Add to Cart</button>
     </div>
    </section>
 
    <section class='category-section' v-if="showHoodies"> 
     <div class="product-container" v-for="(hoodie, index) in products.hoodies" :key="index">
      <h1 class="product-title">{{hoodie.name}}</h1>
      <img :src="hoodie.url" class="product-img">
      <button @click="addHoodieToCart(index)" class="cart-button">Add to Cart</button>
     </div>
    </section>
 
    <section class='category-section' v-if="showPants"> 
     <div class="product-container" v-for="(pant, index) in products.pants" :key="index">
      <h1 class="product-title">{{pant.name}}</h1>
      <img :src="pant.url" class="product-img">
      <button @click="addPantToCart(index)" class="cart-button">Add to Cart</button>
     </div>
    </section>
 
     <section class='category-section' v-if="showShorts"> 
      <div class="product-container" v-for="(short, index) in products.shorts" :key="index">
        <h1 class="product-title">{{short.name}}</h1>
        <img :src="short.url" class="product-img">
        <button @click="addShortToCart(index)" class="cart-button">Add to Cart</button>
        </div>
     </section>
 
     <section class='category-section' v-if="showSocks"> 
      <div class="product-container" v-for="(sock, index) in products.socks" :key="index">
        <h1 class="product-title">{{sock.name}}</h1>
        <img :src="sock.url" class="product-img">
        <button @click="addSockToCart(index)" class="cart-button">Add to Cart</button>
      </div>
     </section>
 
     <section class='category-section' v-if="showShoes"> 
      <div class="product-container" v-for="(shoe, index) in products.shoes" :key="index">
        <h1 class="product-title">{{shoe.name}}</h1>
        <img :src="shoe.url" class="product-img"> 
        <button @click="addShoeToCart(index)" class="cart-button">Add to Cart</button>
      </div>
     </section>
 
    </div>
</template>
 
<script>
  export default {
    data() {
      return {
        showCart: false,
        showHats: false,
        showShirts: false,
        showHoodies: false,
        showPants: false,
        showShorts: false,
        showSocks: false,
        showShoes: false,
        cart: [],
        cartCounter: 0,
        products: {
          hats: [
            {
            name: "Yellow Nike Hat",
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
        },
        home: 1,
      }
    }, 
    methods: {
      addHatToCart(index) {
        this.cart.push(this.products.hats[index])
        this.cartCounter++
        console.log(this.cart)
      },
      addShirtToCart(index) {
        this.cart.push(this.products.shirts[index])
        this.cartCounter++
        console.log(this.cart)
      },
      addHoodieToCart(index) {
        this.cart.push(this.products.hoodies[index])
        this.cartCounter++
        console.log(this.cart)
      },
      addPantToCart(index) {
        this.cart.push(this.products.pants[index])
        this.cartCounter++
        console.log(this.cart)
      },
      addShortToCart(index) {
        this.cart.push(this.products.shorts[index])
        this.cartCounter++
        console.log(this.cart)
      },
      addSockToCart(index) {
        this.cart.push(this.products.socks[index])
        this.cartCounter++
        console.log(this.cart)
      },
      addShoeToCart(index) {
        this.cart.push(this.products.shoes[index])
        this.cartCounter++
        console.log(this.cart)
      },
    },
  }
 
</script>
 
<style lang="scss">
.cart {
  background: lightgrey;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  width: 40rem;
  padding: 2rem;
  padding-bottom: 5rem;
  margin: auto;
  border-radius: 3rem;
  font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
}
.cart-heading {
  font-size: 2rem;
  font-weight: bold;
}
.cart-container {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
  margin-top: 20px;
}
.cart-title {
  font-size: 1.8rem;
  margin-bottom: 20px;
  font-weight: 200;
}
.cart-img {
  height: 50px;
  width: auto;
  padding-right: 1rem;
}
.category-section {
  width: 80rem;
  height: 100%;
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: space-around;
  margin: auto;
  margin-top: 5rem;
}
.product-container {
  width: 30rem;
  background-color: lightgrey;
  border-radius: 2rem;
  margin: 3rem auto;
  padding: 2rem;
  display: flex;
  flex-direction: column;
  justify-content: center;
}
.product-title {
  font-size: 2rem;
  font-weight: bold;
  text-align: center;
  font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
}
.cart-button {
  margin: 1rem auto;
  padding: 1rem;
  width: 8rem;
  position: relative;
  background-color: black;
  border: black;
  border-radius: 10px;
  font-size: 28px;
  color: #FFFFFF;
  width: 200px;
  text-align: center;
  transition-duration: 0.4s;
  text-decoration: none;
  overflow: hidden;
  cursor: pointer;
}

.cart-button:after {
  content: "";
  background: #f1f1f1;
  display: block;
  position: absolute;
  padding-top: 300%;
  padding-left: 350%;
  margin-left: -20px;
  margin-top: -120%;
  opacity: 0;
  transition: all 1.2s;
}

.cart-button:active:after {
  padding: 0;
  margin: 0;
  opacity: 1;
  transition: 0s;
}
 
.product-img {
  height: auto;
  margin: 0;
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
  font-size: 2rem;
  font-weight: bold;
  font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
}
 
.nav-buttons {
    padding: 2rem;
    width: 60rem;
    margin-right: 20rem;
    height: 100%;
    margin: 0 auto;
    display: block;
}
 .check-button:hover {
  background-color: lightgrey;
  color: black;
   box-shadow: 0 22px 26px 0 rgba(0,0,0,0.24), 0 17px 50px 0 rgba(0,0,0,0.19);
}
 
.check-button {
        transition-duration: .5s;
  margin: 1rem;
  background-color: black;
  color: lightgrey;
  border: 20rem;
  border-radius: 10px;
  font-size: 20px;
}
 
.check-button:active {
  transform: translateY(15px);
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
.check-button span {
  cursor: pointer;
  display: inline-block;
  position: relative;
  transition: 0.2s;
}
 
.check-button span:after {
  content: '\00bb';
  position: absolute;
  opacity: 0;
  top: 0;
  right: -20px;
  transition: 0.2s;
}
 
.check-button:hover span {
  padding-right: 25px;
}
 
.check-button:hover span:after {
  opacity: 1;
  right: 0;
}
 
.app {
  display: flex;
  width: 100%;
  height: 100%;
}
 
.home-screen {
    width: 100%;
    background-image: url("./assets/background.jpg");
    background-size: cover;
    text-align: center;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
}
 
.slideset2 {
  height: 50rem; 
  position: relative;
  overflow: hidden;
  }
 
.slideset2 > * {position: absolute; top: 100%; left: 0;
  animation: 12s autoplay2 infinite ease-in-out}
 
  @keyframes autoplay2 {
  0% {top: 100%}
  4% {top: 0%}
  33.33% {top: 0%}
  37.33% {top: -100%}
  100% {top: -100%}
}
 
.slideset2 > *:nth-child(1) {animation-delay: 0s;};
.slideset2 > *:nth-child(2) {animation-delay: 2s;};
.slideset2 > *:nth-child(3) {animation-delay: 4s;};
 
.sliding-gallery {
  height: 50rem; 
  position: relative;
}
.formal {
  height: 50rem;
}
.nike {
  height: 50rem;
}
.casual {
  height: 50rem;
}
</style>