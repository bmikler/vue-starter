<template>
  <div id="app">
    <h1>Witaj w systemie do zapisów na zajęcia</h1>

    <div v-if="!isAuthenticated">
      <login-form @login="login($event)" button-label="Wejdź"></login-form>
      <login-form @login="login($event)" button-label="Wleć"></login-form>
      <login-form @login="login($event)" :button-label="Math.random() < 0.5 ? 'Etykieta A' : 'Etykieta B'"></login-form>
    </div>


    <div v-else>
      <h3>Witaj {{isAuthenticated}}</h3>
      <a @click="logout()">Wyloguj</a>
    </div>

  </div>
</template>

<script>

import "milligram";
import LoginForm from "./LoginForm";

export default {

    components:{LoginForm},

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

      logout() {
        this.isAuthenticated = false;
        this.email = "";
      },

    }

  }

</script>

<style>

</style>
