<template>
  <div id="app">
    <div id="nav">
      <div class="topnav">
        <router-link to="/">홈</router-link>
        <router-link to="/login">로그인</router-link>
        <router-link to="/about">sample</router-link>
        <router-link to="/main">MainPage</router-link>
      </div>

      <!--<router-link v-if="authenticated" to="/secure">Secure</router-link>
      <router-link v-if="authenticated" to="/login" v-on:click.native="logout()" replace>Logout</router-link>
      <router-link v-else to="/login">Login</router-link>
      <router-link to="/about">About</router-link>-->
    </div>
    <router-view @authenticated="setAuthenticated"/>
  </div>
</template>

<script>
    export default {
        name: 'App',
        data() {
            return {
                authenticated: false,
                // this is only for testing purposes no actual app will have this
                // an api call will validate user credentials
                mockAccount: {
                    username: "ameyrupji",
                    password: "P@ssword!"
                }
            }
        },
        methods: {
            setAuthenticated(status) {
                this.authenticated = status;
            },
            logout() {
                this.authenticated = false;
            }
        }
    }
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  margin-bottom: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
  padding-right: 10px;
}

#nav a:not(:first-child) {
  padding-left: 20px; 
}

#nav a.router-link-exact-active {
  color: #42b983;
}

.topnav {
  background-color: #EAEAEA;
  overflow: hidden;
}

/* Style the links inside the navigation bar */
.topnav a {
  float: left;
  padding: 10px 15px;
  text-decoration: none;
  font-size: 9px;
}
</style>
