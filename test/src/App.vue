<template>
  <div id="app">
    <NavBarre class="nav" />
    <div class="div" key="div">
      <Carousel>
        <CarouselSide>
          <img src="./assets/logo.png" alt="" class="imgSlide">
        </CarouselSide>
        <CarouselSide>
          <img src="./assets/logo.png" alt="">
        </CarouselSide>
      </Carousel>
    </div>
    <div id="div1" key="div1"></div>
    <div id="div2" key="div2">
      <Cards />
    </div>
    <div id="div3" key="div3"></div>
    <Footer></Footer>
  </div>
</template>

<script>
// import PartOne from "./components/PartOne"
import NavBarre from './components/NavBarre'
import Cards from './components/Cards'
import Carousel from './components/carousel/Carousel'
import CarouselSide from './components/carousel/CarouselSlide'
import Footer from './components/Footer'

export default {
  name: 'App',
  components: {
    // PartOne,
    NavBarre,
    Cards,
    Footer,
    Carousel,
    CarouselSide
  }
}
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
  text-align: center;
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
  height: 45em;
  background-color: aquamarine;
}
.nav {
  position: fixed;
  top: 0;
  width: 60%;
}
.imgSlide{
  width: 70%;
}
</style>
