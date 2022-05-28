<template>
  <div>
      <h3>Zaloguj się e-mailem: {{email}} </h3>
      <input type="email" v-model="email">
      <button @click="login()">{{ buttonLabel }}</button>
  </div>
</template>

<script>
export default {

    props: ['buttonLabel'],

    mounted () {
      if (!this.buttonLabel){
        this.buttonLabel = "Wejdź"
      }
    },

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
