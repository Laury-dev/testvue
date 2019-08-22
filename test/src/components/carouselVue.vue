<template>
  <div>
    <carousel>
      <carouselSlide v-for="n in slides" :key="n" :index="n-1">
        <img src="../assets/logo.png" alt />
      </carouselSlide>
    </carousel>
  </div>
</template>
<script>
import Carousel from "./carousel/Carousel";
import CarouselSide from "./carousel/CarouselSlide";
export default {
  name: "carouselVue",
  components: {
    Carousel,
    CarouselSide
  },
  data() {
    return {
      slides: 1
    }
  }
}
</script>