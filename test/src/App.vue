<template>
  <div id="app">
    <NavBarre class="nav" />
    <div class="div" key="div">
      <PartOne />
      <!-- <carousel>
        <carousel-slide v-for="n in slides" :key="n" :index="n-1"> -->
          <!-- <div style="position:absolute; left:0; right:0; text-align:center; top:80%; ">
          <p>Bonjour</p>
          </div>-->
          <!-- <img src="./assets/logo2.png" alt />
        </carousel-slide>
      </carousel> -->
    </div>
    <div id="div1" key="div1"></div>
    <div id="div2" key="div2">
      <Cards />
    </div>
    <div id="div3" key="div3"></div>
  </div>
</template>

<script>
import PartOne from "./components/PartOne";
import NavBarre from "./components/NavBarre";
import Cards from "./components/Cards";
import Carousel from "./components/Carousel";
import CarouselSide from "./components/CarouselSlide";

export default {
  name: "App",
  components: {
    PartOne,
    NavBarre,
    Cards,
    Carousel,
    CarouselSide
  },
  data() {
    return {
      slides: 3,  
    }
  }
};
</script>

<style>
body,
html {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
.div {
  padding-top: 5em;
  width: 100%;
  height: 59em;
}
#div1 {
  padding-top: 5em;
  width: 100%;
  height: 60em;
  background-color: lightcoral;
}
#div2 {
  padding-top: 5em;
  width: 100%;
  height: 60em;
  background-color: cadetblue;
}
#div3 {
  padding-top: 5em;
  width: 100%;
  height: 52em;
  background-color: aquamarine;
}
.nav {
  position: fixed;
  top: 0;
  width: 60%;
}
</style>
