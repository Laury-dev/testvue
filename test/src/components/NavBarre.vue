<template>
  <nav class="navDiv">
    <h2>Title Nav</h2>
    <ul class="navUl">
      <li class="navLi" v-for="(link, index) in links" :key="index">          <a v-if="link.active" class="navAActive" v-bind:href="link.href">{{link.name}}</a>
        <a v-else class="navA" v-bind:href="link.href" @click="changeActive(link)">{{link.name}}</a>
      </li>
    </ul>
  </nav>
</template>

<script>
const links = [
  {
    name: "lien1",
    href: "#",
    active: true
  },
  {
    name: "lien2",
    href: "#div1",
    active: false
  },
  {
    name: "lien3",
    href: "#div2",
    active: false
  },
  {
    name: "lien4",
    href: "#div3",
    active: false
  }
]
export default {
  data () {
    return {
      links: links
    }
  },
  methods: {
    changeActive: link => {
      links.forEach(l => {
        l.active = false
      })
      link.active = true
    }
  }
}
</script>

<style>
.navDiv {
  display: flex;
  width: 100%;
  height: 4em;
  background-color: aquamarine;
  padding: 0 1em;
}
.navUl {
  display: flex;
  position: absolute;
  right: 2em;
}
.navLi {
  list-style: none;
  padding: 0.5em 1em;
}
.navA {
  text-decoration: none;
  color: #2c3e50;
}
.navAActive {
  text-decoration: none;
  padding: 1.5em 2em;
  background-color: #2c3e50;
  color: #fff;
}
</style>