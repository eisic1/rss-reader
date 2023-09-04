<template>
        <b-form>
            <div class="row">
                <div class="col-xs-12 col-12">
                    <h1>Registration</h1>
                </div>
            </div>
            <div class="row">
                <div class="col-xs-6 col-6">
                    <input class="first" v-model="fName" type="text" placeholder="First name">
                    <p v-show="err_1">You did not enter a name!</p>
                </div>
                <div class="col-xs-6 col-6">
                    <input class="last" v-model="lName" type="text" placeholder="Last name">
                    <p v-show="err_2">You did not enter a last name!</p>
                </div>
            </div>
            <div class="row">
                <div class="col-xs-12  col-12">
                    <input v-model="email" type="email" placeholder="Email">
                    <p v-show="err_3">You did not enter an email!</p>
                </div>
            </div>
            <div class="row">
                <div class="col-xs-12">
                    <input v-model="password" type="password" placeholder="Password">
                    <p v-show="err_4">You did not enter a password!</p>
                </div>
            </div>
            <div class="row">
                <div class="col-xs-12 col-12">
                    <input v-model="cPassword" type="password" placeholder="Confrim password">
                    <p v-show="err_5">You have not confirmed your password!</p>
                </div>
            </div>
            <div class="row">
                <div class="col-xs-12 col-12">
                    <input @click="registration"  type="submit" value="Register">
                </div>
            </div>
        </b-form>
</template>

<script>
    export default {
        name: 'Register',
        data(){
            return{
                err_1: false,
                err_2: false,
                err_3: false,
                err_4: false,
                err_5: false,
                fName: '',
                lName: '',
                email: '',
                password: '',
                cPassword: ''
            }
        },
        methods: {
            registration(){
                if(!this.fName) this.err_1 = true;
                else this.err_1 = false;
                if(!this.lName) this.err_2 = true;
                else this.err_2 = false;
                if(!this.email) this.err_3 = true;
                else this.err_3 = false;
                if(!this.password) this.err_4 = true;
                else this.err_4 = false;
                if(!this.cPassword) this.err_5 = true;
                else this.err_5 = false;
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
        box-shadow: 0 20px 18px 0 rgba(0, 0, 0, 1), 0 5px 19px 0 rgba(0, 0, 0, 1);
        text-align: left;
    }
    form h1{
        color: white;
        background: #191919;
        font-weight: 500;
        text-align: center;
    }
    form input[type='text'], form input[type='password'], form input[type='email']{
        border: none;
        background: none;
        display: block;
        margin: 15px auto 0 auto;
        padding: 14px 10px;
        width: 100%;
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
        width: 70%;
    }
    form input[type='submit']:hover{
        background-color: #6b6666;
    }
    form p{
        color: #b20808;
    }
</style>