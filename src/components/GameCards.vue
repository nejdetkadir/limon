<template>
  <div class="game-area">
    <h1 class="title">Where is the <span>Limon</span><strong>?</strong></h1>
    <h4 class="description">Lorem ipsum dolor sit amet, consectetur adipisicing elit.</h4>
    <div class="container">
      <card v-for="i in 5" :key="i"></card>
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
