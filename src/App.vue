<template>
  <component :is="activeComponent"></component>
</template>

<script>
  import GameCards from "@/components/GameCards";
  import Celebrate from "@/components/Celebrate";
  import Failure from "@/components/Failure";

  export default {
    components: {
      GameCards,
      Celebrate,
      Failure
    },
    data: () => {
      return{
        activeComponent: 'GameCards'
      }
    }
  }
</script>

<style>
  body{
    font-family: sans-serif;
  }
</style>
