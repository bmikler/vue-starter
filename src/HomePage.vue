<template>

    <div>
      <h3>Witaj {{username}}</h3>
      <a @click="logout()">Wyloguj</a>
    </div>

</template>

<script>
export default {

    props: ['username'],

    methods: {
      logout() {
          this.$emit('logout');
      }
    }
   }

</script>

<style>

</style>
