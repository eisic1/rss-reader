<template>
<!--  <div>
    <div class="row top">
      <Header class="hed" />
    </div>
    <div id="nav" class="row">
      <router-link class="padd" to="/"></router-link> 
        <router-view/> 
    </div> 

    <div class="row bottom">
      <p class="text">Website made by Esmir Isić</p>
    </div>  
  </div> -->
  <div class="app">
    <DynamicLayout>
      <router-view />
    </DynamicLayout>
  </div>
</template>

<script>
/*  import Header from '@/components/Header.vue'

  export default{
    components: {
      Header
    }
  }*/
  import Navigation from '@/components/Navigation.vue'
  import Footer from '@/components/Footer.vue'
  import DynamicLayout from '@/components/DynamicLayout.vue'

  export default {
  name: "App",
  components:{
    Navigation,
    Footer,
    DynamicLayout
  }
};

</script>

<style lang="scss">
/* #app {
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

.right, #nav{
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
} */

* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  font-family: "Raleway", sans-serif;
  font-weight: 400;
}
.app {
  position: relative;
  background-color: #f1f1f1;
}
.container {
  padding: 0 20px;
  max-width: 1140px;
  margin: 0 auto;
}

router-view{
  position: absolute;
}

</style>
