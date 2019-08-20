<template>
  <nav class="navDiv">
    <h2>Title Nav</h2>
    <ul class="navUl">
      <li class="navLi" v-for="(link, index) in links" :key="index">
        <a class="navA" v-bind:href="link.href">{{link.name}}</a>
      </li>
    </ul>
  </nav>
</template>

<script>
const links = [
  {
    name: "lien1",
    href: "#"
  },
  {
    name: "lien2",
    href: "#div1"
  },
  {
    name: "lien3",
    href: "#div2"
  },
  {
    name: "lien4",
    href: "#div3"
  }
];
export default {
  data() {
    return {
      links: links
    };
  }
};
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
</style>