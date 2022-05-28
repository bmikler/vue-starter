<template>
  <div id="app">
    <h1>Witaj w systemie do zapisów na zajęcia</h1>
    
    <div v-if="!isAuthenticated">
      <h3>Zaloguj się e-mailem: {{email}} </h3>
      <input type="email" v-model="email">
      <button @click="login()">Wchodzę</button>
    </div>

    <div v-if="isAuthenticated">
      <h3>Witaj {{email}}</h3>
      <a @click="logout()">Wyloguj</a>
    </div>

  </div>
</template>

<script>

import "milligram";

export default {

    data() {
      return {
        email: '',
        isAuthenticated: false
      }
    },
    
    methods: {
      login() {
        this.isAuthenticated = true;
      },

      logout() {
        this.isAuthenticated = false;
        this.email = "";
      }

    }

  }

</script>

<style>

</style>
