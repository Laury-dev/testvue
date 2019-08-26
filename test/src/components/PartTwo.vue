<template>
  <div>
    <div>
      <h1>Titre Part 2</h1>
      <p class="paragPresent">
        Oportunum est, ut arbitror, explanare nunc causam, quae ad exitium praecipitem
        Aginatium inpulit iam inde a priscis maioribus nobilem, ut locuta est pertinacior
        fama. nec enim super hoc ulla documentorum rata est fides.
        Cuius acerbitati uxor grave accesserat incentivum, germanitate Augusti turgida
        supra modum, quam Hannibaliano regi fratris filio antehac Constantinus iunxerat
        pater, Megaera quaedam mortalis,
        <span v-show="viewText">
          inflammatrix saevientis adsidua, humani cruoris
          avida nihil mitius quam maritus; qui paulatim eruditiores facti processu temporis
          ad nocendum per clandestinos versutosque rumigerulos conpertis leviter addere quaedam
          male suetos falsa et placentia sibi discentes, adfectati regni vel artium nefandarum
          calumnias insontibus adfligebant.
          Principium autem unde latius se funditabat, emersit ex negotio tali. Chilo ex vicario
          et coniux eius Maxima nomine, questi apud Olybrium ea tempestate urbi praefectum, vitamque
          suam venenis petitam adseverantes inpetrarunt ut hi, quos suspectati sunt, ilico rapti
          conpingerentur in vincula, organarius Sericus et Asbolius palaestrita et aruspex Campensis.
        </span>
      </p>
      <button class="btnDisplayParag" v-on:click="view">
        <strong>En lire plus</strong>
      </button>
    </div>
    <div>
      <ul>
        <li v-for="(image , index) in tabRefImages" :key="index">
          <img v-bind:src='"../assets/"+image' alt="" class="imgIllus">
        </li>
      </ul>
    </div>
  </div>
  <!-- A realiser pour la partie deux -->
</template>

<script>
export default {
  name: "PartOne",
  data () {
    return {
      tabRefImages: ['next.png','prev.png'],
      viewText: false
    }
  },
  methods: {
    view() {
      this.viewText = !this.viewText;
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
div {
  text-align: center;
  color: #fff;
}
h1,
h2 {
  font-weight: normal;
  text-decoration: underline;
}
.paragPresent {
  padding: 1em 3em;
}
.btnDisplayParag {
  padding: 0.5em;
  font-size: 1em;
  border-radius: 0.5em;
  background-color: #fff;
  color: #2c3e50;
}
.imgIllus{
  width: 60px;
  height: 60px;
}
</style>
