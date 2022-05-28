<template>
  <div>
    <h1>Twój email to: {{ email }}.</h1>
    <h2>Twój email to: {{ email }}.</h2>
    <h3>Ilość znaków: {{email.length}}</h3>
    <br>
    <input type = "text" v-model = "email" >

  </div>
</template>

<script>
export default {
  data() {
    return {
      email: '',
    }
  }

}
</script>

<style>

</style>
