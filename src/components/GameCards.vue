<template>
  <div class="game-area">
    <h1 class="title">Where is the <span>Limon</span><strong>?</strong></h1>
    <h4 class="description">Lorem ipsum dolor sit amet, consectetur adipisicing elit.</h4>
    <div class="container">
      <card v-for="card in cards" :key="card.id" :card="card"></card>
    </div>
    <div class="container">
      <default-card></default-card>
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
        cards: [
          {
            id: 1,
            component: "app-cards",
            img: require('../assets/1.jpg')
          },
          {
            id: 2,
            component: "app-cards",
            img: require('../assets/2.jpg')
          },
          {
            id: 3,
            component: "app-cards",
            img: require('../assets/3.jpg')
          },
          {
            id: 4,
            component: "app-cards",
            img: require('../assets/4.jpg')
          }
        ]
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

</style>
