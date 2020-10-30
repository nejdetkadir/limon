<template>
  <transition-group enter-active-class="animate__animated animate__slideInRight">
    <component :is="activeComponent" @activeComponentEvent="activeComponent = $event" key="mainComponent"></component>
    <canvas id="my-canvas" key="canvas" v-show="activeComponent === 'Celebrate'"></canvas>
  </transition-group>
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
