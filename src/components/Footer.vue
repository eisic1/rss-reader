<template>
<footer>
  <div class="row text">
    <div class="col-xs-12 col-12">
      <p>Website made by Esmir Isić</p>
    </div>
  </div>
</footer>
</template>

<script>
    export default {
        name: "Footer"
    }
</script>

<style scoped>
  footer{
    position: fixed;
    bottom: 0;
    width: 100%;
  }
  .text{
    background-color: rgba(0, 0, 0, 0.8);
    color: white;
    text-align: center;

  }
  p{
    margin-top: 10px;
    font-size: 18px;
  }
</style>