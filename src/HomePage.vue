<template>

    <div>
      <h3>Witaj {{username}}</h3>
      <a @click="logout()">Wyloguj</a>
    </div>

</template>

<script>

import "milligram";

export default {

    props: ['username'],

    methods: {
      logout() {
          this.$emit('logout', false);
      }
    }
   }

</script>

<style>

</style>
