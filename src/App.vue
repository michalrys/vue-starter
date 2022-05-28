<template>
  <div>
    <h1>Witaj</h1>

    <div v-if="!loggedIn">
      <label>Zaloguj się: </label>
      <input type = "text" @keyup.enter="logMeIn()" v-model = "email" >
      <button @click = "logMeIn()">Zaloguj się</button>
    </div>
    <div v-else>
      <h2>Witaj {{email}}</h2>
      <a @click="logMeOut">Wyloguj się</a>
    </div>


  </div>
</template>

<script>
import "milligram";

export default {
  data() {
    return {
      email: '',
      loggedIn: false,
    }
  },
  methods: {
    logMeIn() {
      this.loggedIn = true;
    },
    logMeOut() {
      this.loggedIn = false;
      this.email = '';
    }
  }
}
</script>

<style>

</style>
