<template>
    <div class="back">
        <Login />
    </div>
</template>

<script>

import Login from '../components/LoginForm.vue'

export default {
    components:{
        Login
    }
    
}
</script>

<style scoped>
    .back{
        height: 100vh;
        background-color: #333333;
    }
</style>