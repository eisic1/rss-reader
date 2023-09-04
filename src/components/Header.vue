<template>
  <div class="container">
    <div class="image">
        <img class="slika" alt="" src="../assets/logo-rss.png">
    </div>
    <div class="text">
      <p>RSS Reader</p>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'Header'
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="css">
  .container {
    display: flex;
  /*  background-color: #262626; */
  }
  img {
    max-width: 100%;
    padding-left: 5px;
  }
  .text {
    font-size: 25px;
    padding: 5px 0 0 10px;
    color: #b3b300;
    font-family: "Times New Roman", Times, serif;
  }
</style>