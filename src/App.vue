<template>
  <div id="app">
    <h1>E-mail: {{ email}} </h1>

    <div v-if="email.length < 10">Ale masz krótki adres!</div>
    <div v-else-if="email.length < 15">Twój adres e-mail jest w sam raz.</div>
    <div v-else class="red">Twój adres e-mail jest stanowczo za długi.</div>
    <input type="email" v-model="email">

    <button @click="alertMyEmail()">Send</button>

  </div>
</template>

<script>



export default {

    data() {
      return {
        email: ''
      }
    },
    
    methods: {
      alertMyEmail() {
        alert(this.email);
      }
    }

  }

</script>

<style>
.red {
  color: red;
}
</style>
