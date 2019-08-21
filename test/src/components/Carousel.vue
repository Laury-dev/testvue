<template>
  <div>
    <h2>Carousel</h2>
    <div class="carousel">
    <slot></slot>
    <button class="carousel__nav carousel__prev" @click.prevent="prev"></button>
    <button class="carousel__nav carousel__next" @click.prevent="next"></button>
    <div class="pagination">
    <button v-for="n in slidesCount" @click="goto(n-1)" :key="n" :class="{active: n-1 === index}"></button>
    </div>
  </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      index: 0,
      slides: [],
      direction: null
    }
  },
  mounted () {
    this.slides = this.$children
    this.slides.forEach((slide, i) => {
      slide.index = i
    })
  },
  watch: {
    slides (slides) {
      if (this.index >= this.slidesCount) {
        this.index = this.slidesCount - 1 
      }
    }
  },
  computed: {
    slidesCount () {
      return this.slides.length
    }
  },
  methods: {
    next () {
      this.index++
      this.direction = 'right'
      if (this.index >= this.slidesCount) {
        this.index = 0
      }
    },
    prev () {
      this.index--
      this.direction = 'left'
      if (this.index < 0) {
        this.index = this.slidesCount - 1
      }
    },
    goto (index) {
      this.direction = index > this.index ? 'right' : 'left'
      this.index = index
    }
  }
}
</script>
<style>
.carousel{
  position: relative;
}
.carousel__nav{
  position: absolute;
  top: 50%;
  left: 1em;
  background: #000;
  width: 60px;
  height: 60px;
  border: none;
}
.carousel__nav.carousel__next{
  right: 1em;
  left: auto;
  background:  #000;
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