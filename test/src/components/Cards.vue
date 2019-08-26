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
/* Probleme de centrage des cards sur le grand format*/
.cardDiv {
  text-align: center;
}
.cardH2 {
  padding-bottom: 2em;
}
.cardUl {
  /* Probleme */
  display: flex;
  width: 90%;
  margin: auto 15%;
  padding: 0;
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
  margin: auto 2em auto 2em;
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

@media screen and (max-width: 1100px) {
  .cardDiv {
    margin: 0; 
  }
  .cardUl {
    padding: 0;
    margin: 0 10%;
    width: 80%;
  }
  .card {
    margin: auto 2em auto 1.5em;
    width: 50%;
  }
}

@media screen and (max-width: 780px) {
  .cardUl {
    flex-direction: column;
    width: 91%;
  }
  .card {
    width: 250px;
    height: 100px;
    padding: 50px 50px;
    margin: auto auto 1em auto;
  }
}
</style>