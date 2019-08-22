<template>
  <div class="cardDiv">
    <h2 class="cardH2">Cards</h2>
    <ul class="cardUl">
      <li v-for="(card, index) in cards" :key="index" v-on:click="moveCard(card)" class="cardLi">
        <transition name="flip">
          <p v-if="!card.move" key="front" class="card">{{card.front}}</p>
          <p v-else key="back" class="card">
            {{card.back.titre}}
            <br />
            {{card.back.parag}}
          </p>
        </transition>
      </li>
    </ul>
  </div>
</template>
<script>
const cards = [
  {
    front: 'Titre front 1',
    back: {
      titre: 'Titre back 1',
      parag: 'Parag back 1'
    },
    move: false
  },
  {
    front: 'Titre front 2',
    back: {
      titre: 'Titre back 2',
      parag: 'Parag back 2'
    },
    move: false
  },
  {
    front: 'Titre front 3',
    back: {
      titre: 'Titre back 3',
      parag: 'Parag back 3'
    },
    move: false
  }
]
export default {
  data () {
    return {
      cards: cards
    }
  },
  methods: {
    moveCard: card => {
      card.move = !card.move
    }
  }
}
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
.cardLi{
  list-style: none;
}
.card {
  display: block;
  width: 150px;
  height: 175px;
  padding: 80px 50px;
  background-color: #fff;
  border-radius: 7px;
  margin: 1em;
  text-align: center;
  line-height: 27px;
  cursor: pointer;
  position: relative;
  color: #2c3e50;
  font-weight: 600;
  font-size: 20px;
  -webkit-box-shadow: 9px 10px 22px -8px rgba(209, 193, 209, 0.5);
  -moz-box-shadow: 9px 10px 22px -8px rgba(209, 193, 209, 0.5);
  box-shadow: 9px 10px 22px -8px rgba(209, 193, 209, 0.5);
  will-change: transform;
}
.flip-enter-active {
  transition: all 0.4s ease;
}
.flip-leave-active {
  display: none;
}
.flip-enter,
.flip-leave {
  transform: rotateY(180deg);
  opacity: 0;
}
</style>