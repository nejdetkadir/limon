<template>
  <div class="game-area">
    <h1 class="title">Where is the <span>Limon</span><strong>?</strong></h1>
    <h4 class="description">Lorem ipsum dolor sit amet, consectetur adipisicing elit.</h4>
    <div class="container">
      <transition-group class="card-container" enter-active-class="animate__animated animate__flip" appear>
        <card @click.native="selectedCard = card.id" v-for="card in cards" :key="card.id" :card="card" :class="{'shadow' : selectedCard == card.id}"></card>
      </transition-group>

    </div>
    <div class="container">
      <transition mode="out-in" leave-active-class="animate__animated animate__flipInY">
        <component :is="activeCard" @click.native="showCard(answer)" :card="answer"></component>
      </transition>
    </div>
  </div>
</template>

<script>
  import Card from "@/components/Card";
  import DefaultCard from "@/components/DefaultCard";

  export default {
    components: {
      Card,
      DefaultCard
    },
    data: () => {
      return{
        activeCard: 'DefaultCard',
        answer: {},
        selectedCard: null,
        cards: [
          {
            id: 1,
            component: "card",
            img: require('../assets/1.jpg')
          },
          {
            id: 2,
            component: "card",
            img: require('../assets/2.jpg')
          },
          {
            id: 3,
            component: "card",
            img: require('../assets/3.jpg')
          },
          {
            id: 4,
            component: "card",
            img: require('../assets/4.jpg')
          }
        ]
      }
    },
    created() {
      let answer = Math.floor(Math.random() * this.cards.length);
      this.answer = this.cards[answer];
      console.log(this.answer.id + ': id')
    },
    methods: {
      showCard(a) {
        if (this.selectedCard) {
          this.activeCard = a.component;
          setTimeout(() => {
            if (a.id === this.selectedCard) {
              this.$emit('isCorrectEvent', 'Celebrate');
            } else {
              this.$emit('isCorrectEvent', 'Failure');
            }
          }, 1800);
        } else {
          alert('Please guess a card and select it!');
        }

      }
    }
  }
</script>

<style scoped>
  .title{
    text-align: center;
    color: rosybrown;
  }
  .title span{
    color: mediumpurple;
  }
  .title strong{
    color: darkred;
  }
  .description{
    text-align: center;
    color: gray;
  }
  .container{
    display: flex;
    justify-content: center;
    align-items: center;
    margin-top: 50px;
  }
  .card-container{
    display: flex;
    justify-content: center;
    align-items: center;
    margin-top: 50px;
  }
  .shadow{
    box-shadow: 0px 5px 48px #30969f !important;
    transition: box-shadow .5s;
  }
</style>
