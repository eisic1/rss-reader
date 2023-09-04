<template>
   <div>  
       <Navigation />
       <slot></slot>
       <Footer />
    </div>
</template>

<script>
    import Navigation from'./Navigation.vue'
    import Footer from './Footer.vue'
    export default{
        name: "DymanicLayout",
        components:{
            Navigation,
            Footer
        }
    }
</script>

<style>

</style>
