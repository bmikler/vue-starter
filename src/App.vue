<template>
  <div id="app">
    <h1>Witaj w systemie do zapisów na zajęcia</h1>

    <div v-if="!isAuthenticated">
      <login-form @login="login($event)"></login-form>
    </div>

    <div v-else>
      <home-page @logout="logout($event)" :username = this.isAuthenticated></home-page>
    </div>

  </div>
</template>

<script>

import "milligram";
import LoginForm from "./LoginForm";
import HomePage from "./HomePage.vue";

export default {

    components:{LoginForm, HomePage},

    data() {
      return {
        email: '',
        isAuthenticated: false
      }
    },
    
    methods: {
      login(username) {
        this.isAuthenticated = username;
      },

      logout(status) {
        this.isAuthenticated = status;
      },

    }

  }

</script>

<style>

</style>
