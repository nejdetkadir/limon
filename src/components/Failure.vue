<template>
  <div class="container">
    <h1>You lose :(</h1>
    <button @click="newGame()">NEW GAME</button>
  </div>
</template>

<script>
  export default {
    methods: {
      newGame() {
        this.$emit('activeComponentEvent', 'GameCards');
      }
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
    background-color: darkred;
  }
  .container h1{
    text-align: center;
    color: white;
    font-size: 333%;
  }
  .container button{
    width: 200px;
    background-color: #fff;
    color: darkred;
    border: 1px solid brown;
    height: 50px;
    font-size: 15px;
    border-radius: 5px;
    outline: none;
    transition: all .5s;
  }
  .container button:hover{
    background-color: lightgreen;
    color: #fff;
    transition: all .5s;
  }
</style>
