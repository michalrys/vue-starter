<template>
  <div>
    <h1>Witaj</h1>

<!--    <div v-if="!email">-->
    <div v-if="authenticatedUsername == ''">
      <login-form @login="enter($event)" button-label="Wejdź"></login-form>
      <login-form @login="enter($event)" button-label="Wleć"></login-form>
      <login-form @login="enter($event)" :button-label="Math.random() < 0.5 ? 'Etykieta A' : 'Etykieta B'"></login-form>
      <login-form @login="logMeIn($event)" button-label="Zaloguj sie"></login-form>
    </div>
    <div v-else>
      <log-out-form :email="authenticatedUsername" @logout="logMeOut()">OK</log-out-form>
    </div>


  </div>
</template>

<script>
import "milligram";
import LoginForm from "./LoginForm";
import Logged from "@/LogOutForm";
import LogOutForm from "@/LogOutForm";

export default {
  components: {LogOutForm, Logged, LoginForm},

  data() {
    return {
      authenticatedUsername: ''
    }
  },

  methods: {
    logMeIn(username) {
      this.authenticatedUsername = username;
    },
    logMeOut() {
      this.authenticatedUsername = '';
    }
  }
}
</script>

<style>

</style>
