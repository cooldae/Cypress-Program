<template>

    <div id="login">
        <div class="box">
            <h3 style="color: red;">로그인페이지 (통합)</h3>
            <h1>Sign In</h1>
            <div class="form-inputs">
                <input class="loginBox" type="text" id="username" name="username" v-model="input.username" placeholder="Username" />
            </div>
            <div class="form-inputs">
                <input class="loginBox" type="password" id="password" name="password" v-model="input.password" placeholder="Password"/>
            </div>
            <button type="button" style="width:310px; height:45px; color:#FFFFFF; background-color:#000030" v-on:click="login()">Login</button>
            <div>
                <div class=footer style="color:#000000" >Create Account</div>
                <div class=footer>Forgot Username?</div>
                <div class=footer>Forgot Password?</div>
            </div>
        </div>

    </div>
</template>

<script>
    export default {
        name: 'Login',
        data() {
            return {
                input: {
                    username: "",
                    password: ""
                }
            }
        },
        methods: {
            login() {
                if(this.input.username != "" && this.input.password != "") {
                    // This should actually be an api call not a check against this.$parent.mockAccount
                    if(this.input.username == this.$parent.mockAccount.username && this.input.password == this.$parent.mockAccount.password) {
                        this.$emit("authenticated", true);
                        this.$router.replace({ name: "Secure" });
                    } else {
                        console.log("The username and / or password is incorrect");
                    }
                } else {
                    console.log("A username and password must be present");
                }
            }
        }
    }
</script>

<style>

#login .footer {
    font-size: 10px;
    padding-right: 8px;
    text-align: center;
    float: left;
    margin-left:40px;
    margin-top: 30px;
    color: #FFBB00;
}
#login .loginBox {
    width: 300px;
    height: 30px;
    font-size: 12px;
}
#login .form-inputs {
    padding-bottom: 35px;
}

#login .form-inputs label {
    padding-right: 20px;
}

#login .box {
    width: 400px;
    height: 400px;
    border: 2px solid black;
    margin: auto;
    margin-top: auto;
}
</style>