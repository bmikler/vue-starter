<template>
  <div>
      <h3>Zaloguj się e-mailem: {{email}} </h3>
      <input type="email" v-model="email">
      <button @click="login()">{{ buttonLabel }}</button>
  </div>
</template>

<script>

import "milligram";

export default {

    props: ['buttonLabel'],

    data() {
      return {
        email: ''
      }
    },
    
    methods: {
      login() {
          this.$emit('login', this.email);
      }
    }
  }

</script>

<style>

</style>
