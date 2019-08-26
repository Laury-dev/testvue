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
/* Attention defaut de responsivité pour le titre */
.footer {
  background-color: #2c3e50;
  color: #fff;
  text-align: center;
  width: 100%;
}
.footerPartOne {
  align-items: center;
  display: flex;
  width: 100%;
}
.footerH2 {
  padding-left: 12em;
}
.footerUl {
  display: flex;
  position: absolute;
  bottom: -187.6em;
  right: 12em;
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
@media screen and (max-width: 1100px){
  .footerH2 {
    padding-left: 5%;
  }
  .footerUl {
    bottom: -189em;
    right: 5%;
  }
}
@media screen and (max-width: 780px){
  .footerH2 {
    padding-left: 5%;
  }
  .footerUl {
    bottom: -189em;
    right: 1em;
  }
}
</style>