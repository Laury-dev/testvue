<template>
  <div class="partTwoDiv">
    <div>
      <h2 class="partTwoH2">Titre Part 2</h2>
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
    <div class="partTwodivImg">
      <!-- Attention probleme avaec la lecture des images -->
      <ul class="partTwoUl">
        <li v-for="(image, index) in tabRefImages" :key="index" class="partTwoLi">
          <img :src='"../assets/"+image' alt="image">
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "PartOne",
  data () {
    return {
      tabRefImages: ['next.png', 'prev.png', 'logo.png'],
      viewText: false
    }
  },
  methods: {
    view () {
      this.viewText = !this.viewText
    }
  }
}
</script>

<style>
.partTwoDiv {
  text-align: center;
  color: #fff;
}
.partTwoH2 {
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
.partTwoUl{
  display: flex;
  height: 160px;
}
.partTwoLi{
  list-style: none;
  display: block;
  height: 100%;
  width: 30%;
}
.partTwodivImg{
  margin-top: 4em;
}
</style>
