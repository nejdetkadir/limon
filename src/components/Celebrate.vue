<template>
  <div class="container">
    <h1>You know right :)</h1>
    <button @click="newGame()">NEW GAME</button>
  </div>
</template>

<script>
import ConfettiGenerator from "confetti-js";
let confetti;
export default {
  methods: {
    newGame() {
      confetti.clear();
      this.$emit('activeComponentEvent', 'GameCards');
    }
  },
  created() {
    const confettiSettings = { target: 'my-canvas' };
    confetti = new ConfettiGenerator(confettiSettings);
    confetti.render();
  }
}
</script>

<style scoped>
.container{
  position: absolute;
  top: 0px;
  left: 0px;
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
.container h1{
  text-align: center;
  color: darkgreen;
  font-size: 333%;
  opacity: .5;
}
.container button{
  width: 200px;
  background-color: #fff;
  color: darkred;
  border: 1px solid darkgreen;
  height: 50px;
  font-size: 15px;
  border-radius: 5px;
  outline: none;
  transition: all .5s;
}
.container button:hover{
  background-color: darkgreen;
  color: #fff;
  transition: all .5s;
}
</style>
