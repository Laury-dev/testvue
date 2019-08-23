<template>
  <div class="footer">
    <div class="footerPartOne">
      <h2 class="footerH2">Titre du footer</h2>
      <ul class="footerUl">
        <li v-for="(link, index) in links" :key="index" class="footerLi">
          <a href="#" class="footerA">{{ link }}</a>
        </li>
      </ul>
    </div>
    <div>
      <p>Pargraphe d'explication</p>
    </div>
    <div>
      <p class="footerEnd">
        <strong>2019 - FIN</strong>
      </p>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      links: ["Home", "Contact", "Autre"]
    }
  }
}
</script>

<style>
.footer {
  background-color: #2c3e50;
  color: #fff;
  text-align: center;
}
.footerPartOne {
  align-items: center;
  display: flex;
}
.footerH2 {
  padding-left: 35%;
}
.footerUl {
  display: flex;
  padding-left: 12%;
}
.footerLi {
  list-style: none;
}
.footerA {
  text-decoration: none;
  color: #fff;
  padding: 0 1em;
}
.footerEnd {
  padding: 0;
  margin: 0;
}
</style>