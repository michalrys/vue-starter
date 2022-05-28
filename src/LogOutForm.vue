<template>
  <div>
    <h2>Witaj {{email}}</h2>
    <a @click="logMeOut()">Wyloguj się</a>
  </div>
</template>

<script>
export default {
  props: ['email'],

  methods: {
    logMeOut() {
      this.$emit('logout');
    }
  }
}
</script>

<style>

</style>
