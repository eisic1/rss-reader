<template>
        <b-form>
            <div class="row">
                    <div class="col-xs-12 col-12 title">
                        <h1>Log in</h1>
                    </div>
            </div>
            <div class="form-row">
                    <div class="col-xs-12 col-12 title">
                        <input v-model="email" type="text" placeholder="email">
                        <p v-show="error_1">You did not enter an email !</p>
                    </div>
            </div>
            <div class="form-row">
                    <div class="col-xs-12 col-12 title">
                        <input v-model="password" type="password" placeholder="password">
                        <p v-show="error_2">You did not enter a password !</p>
                    </div>
            </div>
            <div class="form-row">
                    <div class="col-xs-12 col-12 title">
                        <input @click="submit" type="submit" value="Login">
                    </div>
            </div>
            <div class="row">
                    <div class="col-xs-12 col-12 title">
                        <span>Forgot <a href="">password</a></span>
                    </div>
            </div>
        </b-form>
</template>

<script>

export default{
    name: 'Login',
    data(){
        return{
            error_1: false,
            error_2: false,
            email: '',
            password: ''
        }
    },
    methods:{
        submit(){
            if(!this.email) this.error_1 = true;
            else this.error_1 = false;
            if(!this.password) this.error_2 = true;
            else this.error_2 = false;
        }
    }
}
</script>


<style scoped>
    *{
        margin: 0;
        padding: 0;
        box-sizing: border-box;

    }
    form{
        padding: 40px;
        position: fixed;
        top: 50%;
        left: 50%;
        transform: translate( -50%, -50%);
        background: #191919;
        text-align: center;
        box-shadow: 0 20px 18px 0 rgba(0, 0, 0, 1), 0 5px 19px 0 rgba(0, 0, 0, 1);
    }
    form h1{
        color: white;
        background: #191919;
        font-weight: 500;
    }
    form input[type='text'], form input[type='password']{
        border: none;
        background: none;
        display: block;
        margin: 20px auto 0 auto;
        text-align: center;
        padding: 14px 10px;
        width: 90%;
        outline: none;
        color: white;
        border-bottom: 1px solid #6b6666;
    }
    form input[type='submit']{
        background: none;
        display: block;
        margin: 45px auto 20px auto;
        text-align: center;
        border: 2px solid #6b6666;
        padding: 14px 20px;
        outline: none;
        color: white;
        border-radius: 24px;
        cursor: pointer;
        width: 60%;
    }
    form input[type='submit']:hover{
        background-color: #6b6666;
    }
    form span{
        color: grey;
        font-size: 15px;
    }
    form a{
        font-size: 15px;
        color: #b20808;
        text-transform: none;
    }
    form p{
        color: #b20808;
    }

</style>
