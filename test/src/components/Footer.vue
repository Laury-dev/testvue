<template>
  <div class="footer">
    <div class="footerPartOne">
      <h2 class="footerH2">Titre du footer</h2>
      <ul class="footerUl">
        <li v-for="(link, index) in links" :key="index" class="footerLi">
          <a href="link.lien" class="footerA">{{ link.Name }}</a>
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
      links: [
        {
          Name: "Home",
          lien: '#div'
        },
        {
          Name: "Contact",
          lien: '#'
        },
        {
          Name: "Autre",
          lien: '#'
        }]
    }
  }
}
</script>

<style>
/*Attention defaut de responsivité pour le titre 
(passe sur deux lignes)*/
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
  bottom: -189.8em;
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
    bottom: -187.8em;
    right: 5%;
  }
}
@media screen and (max-width: 780px){
  .footerH2 {
    padding-left: 5%;
  }
  .footerUl {
    bottom: -188.8em;
    right: 1em;
  }
}
</style>