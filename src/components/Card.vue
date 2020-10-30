<template>
  <div class="card">
    <img height="200" src="../assets/1.jpg">
  </div>
</template>

<script>
  export default {

  }
</script>

<style scoped>
  .card{
    width: 200px;
    height: 200px;
    border-radius: 5px;
    border: 1px solid #666;
    transition: box-shadow .5s;
    margin-left: 15px;
  }
  .card:hover{
    box-shadow: 0px 5px 48px #666;
    transition: box-shadow .5s;
  }
  .card:first-child{
    margin-left: 0px;
  }
</style>
