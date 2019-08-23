<template>
  <transition name="slide">
    <div class="slideDiv" v-show="visible">
      <slot></slot>
    </div>
  </transition>
</template>

<script>
export default {
  name: "CarouselSlide",
  data() {
    return {
      index: 0
    }
  },
  computed: {
    visible() {
      return this.index === this.$parent.index
    }
  }
}
</script>

<style>
.slideDiv{
  padding-top: 15em;
}
.slide-enter-active {
  animation: slideRightIn 1s;
}
.slide-leave-active {
  animation: slideRightOut 1s;
  position: absolute;
  left: 0;
  top: 0;
}
@keyframes slideRightIn {
  from {
    transform: translateX(100%);
  }
  to {
    transform: translateX(0);
  }
}
@keyframes slideRightOut {
  from {
    transform: translateX(0);
  }
  to {
    transform: translateX(-120%);
  }
}
.slide-left-enter-active {
  animation: slideLeftIn 1s;
}
.slide-left-leave-active {
  animation: slideLeftOut 1s;
  position: absolute;
  right: 0;
  top: 0;
}
@keyframes slideLeftIn {
  from {
    transform: translateX(-100%);
  }
  to {
    transform: translateX(0);
  }
}
@keyframes slideLeftOut {
  from {
    transform: translateX(0);
  }
  to {
    transform: translateX(120%);
  }
}
</style>