<template>
    <div class="back">
        <Register />
    </div>
</template>

<script>
import Register from '../components/RegisterForm.vue'

export default {
    components: {
        Register
    }
}
</script>

<style scoped>
    .back{
        height: 100vh;
        background-color: #333333;
    }
</style>