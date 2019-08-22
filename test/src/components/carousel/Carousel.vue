<template>
  <div class="carousel">
    <slot></slot>
    <button class="carouselNav carouselPrev" v-on:click.prevent="prev"></button>
    <button class="carouselNav carouselNext" v-on:click.prevent="next">next</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      index: 0,
      slides: this.$children
    }
  },
  mounted() {
    this.slides = this.$children
    this.slides.forEach((slide, i) => {
      slide.index = i
    })
  },
  methods: {
    next () {
      this.index++
      if (this.index >= this.slidesCount) {
        this.index = 0
      }
    },
    prev () {
      this.index--
      if (this.index < 0) {
        this.index = this.slidesCount-1
      }
    }
  },
  computed: {
   slidesCount () {
     return this.slides.length
   }
  }
}
</script>
<style>
.carousel{
  position: relative;
}
.carouselNav{
  position: absolute;
  top: 50%;
  left: 1em;
  background: url("../../assets/prev.png");
  width: 60px;
  height: 60px;
  border: none;
}
.carouselNav .carouselNext{
  right: 5em;
  left: auto;
  background:  url("../../assets/next.png");
}
.pagination{
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  text-align: center;
}
.pagination button{
  display: inline-block;
  width: 12px;
  height: 12px;
  border-radius: 50%;
  border-style: none;
  background-color: #000;
  border-color: #000;
  opacity: 0.8;
  margin: 0 1.5px;
}
.pagination button.active{
  background: rgb(128, 128, 128);
}
</style>