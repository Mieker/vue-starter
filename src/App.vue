<template>
  <div>
    <h1>Twoj adres e-mail to {{email}}</h1>
    <div v-if="email.length < 10 ">Ale masz krotki adres!</div>
    <div v-else-if="email.length < 15 ">Twoj adres jest w sam raz</div>
    <div v-else>Twoj adres jest za dlugi!!</div>

    <input type="email" v-model="email">
  </div>
</template>

<script>
export default {
  data () {
    return {
      email: ''
    };
  }
}
</script>

<style>

</style>
