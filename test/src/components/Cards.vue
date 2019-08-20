<template>
  <div class="cardDiv">
    <h2 class="cardH2">Cards</h2>
    <ul class="cardUl">
      <li v-for="(card, index) in cards" :key="index" class="card" @click="card.move = !card.move">
          <p v-if="!card.move">{{card.front}}</p>
          <p v-else>
            {{card.back.titre}}
            <br />
            {{card.back.parag}}
        </p>
      </li>
    </ul>
  </div>
</template>
<script>
const cards = [
  {
    front: "Titre front 1 ",
    back: {
      titre: "Titre back 1",
      parag: "Parag back 1"
    },
    move: false
  },
  {
    front: "Titre front 2",
    back: {
      titre: "Titre back 2",
      parag: "Parag back 2"
    },
    move: false
  },
  {
    front: "Titre front 3",
    back: {
      titre: "Titre back 3",
      parag: "Parag back 3"
    },
    move: false
  }
];
export default {
  data() {
    return {
      cards: cards
    };
  }
};
</script>

<style>
.cardDiv {
  text-align: center;
}
.cardH2 {
  padding-bottom: 2em;
}
.cardUl {
  display: flex;
}
.card {
  text-align: center;
  list-style: none;
  width: 10em;
  height: 15em;
  border-radius: 1em;
  margin: 0 4em 0 4em;
  background-color: white;
}
</style>