<template>
  <div id="app">
    <h1>Witaj w systemie do zapisów na zajęcia</h1>
    
    <div v-if="logged == false">
      <h3>Zaloguj się e-mailem: {{email}} </h3>
      <input type="email" v-model="email">
      <button @click="login()">Wchodzę</button>
    </div>


    <div v-if="logged == true">
      <h3>Witaj {{email}}</h3>
      <button @click="logout()">Wyloguj</button>
    </div>

  </div>
</template>

<script>



export default {

    data() {
      return {
        email: '',
        logged: false
      }
    },
    
    methods: {
      alertMyEmail() {
        alert(this.email);
      },

      login() {
        this.logged = true;
      },

      logout() {
        this.logged = false;
        this.email = "";
      }

    }

  }

</script>

<style>
.red {
  color: red;
}
</style>
