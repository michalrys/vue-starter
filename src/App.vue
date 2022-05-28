<template>
  <div>
    <h1>Witaj</h1>

<!--    <div v-if="!email">-->
    <div v-if="email == ''">
      <login-form @login="logMeIn($event)"></login-form>
    </div>
    <div v-else>
      <h2>Witaj {{email}}</h2>
      <a @click="logMeOut">Wyloguj się</a>
    </div>


  </div>
</template>

<script>
import "milligram";
import LoginForm from "./LoginForm";

export default {
  components: {LoginForm},

  data() {
    return {
      email: ''
    }
  },

  methods: {
    logMeIn(username) {
      this.email = username;
    },
    logMeOut() {
      this.email = '';
    }
  }
}
</script>

<style>

</style>
