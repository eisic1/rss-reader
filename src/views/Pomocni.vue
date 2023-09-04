<template>
  <div>
    <div class="row top">
      <Header class="hed" />
    </div>
    <div id="nav" class="row">
      <div class="col-3 left">
      <router-link class="padd" to="/">+ &nbsp&nbsp All feeds</router-link> <br>
      <router-link class="padd" to="/about">+ &nbsp&nbsp Add feed</router-link>
      </div>
      <div class="col-9 right">
        <router-view/>
      </div>
    </div> 

    <div class="row bottom">
      <p class="text">Website made by Esmir Isić</p>
    </div>  
  </div>
</template>

<script>
  import Header from '@/components/Header.vue'

  export default{
    components: {
      Header
    }
  }

</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
 
.hed{
  margin-left: 10px;
  padding: 10px 0 0 10px;
}

.top, .bottom{
  background-color:  #262626;
}

.left{
  background-color: #4d4d4d;
  height: 636px;
  border-right: 2px solid #4d4d4d;
  box-shadow: 0 0 10px 3px #4d4d4d;
}

.right{
  background-color: #333333;
  height: 636px;
}


  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }

  .text{
    color: white;
  }

.bottom{
  text-align: center;
}

.prefiks{
  padding: 10px;
}

.padd{
  padding: 20px;
  text-decoration: none;
  color: white;
}

</style>
