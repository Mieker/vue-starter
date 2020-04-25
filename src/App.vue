<template>
  <div>
    <h1>Witaj w systemie do zapisow na zajecia</h1>
    <div v-if="logButtonPressed == false">
      <p>Zaloguj sie e-mailem</p>
      <input type="email" v-model="email">
      <button @click="logButtonPressed = true">Wchodze</button>
    </div>
    <div v-else>
      <h2>Witaj {{email}}</h2>
      <a href="">Wyloguj</a>
    </div>
   </div>
</template>

<script>
export default {
  data () {
    return {
      email: '',
      logButtonPressed: false
    };
  },

  methods: {
    alertMyEmail() {
      alert(this.email);
    },
    
  }
}
</script>

<style>

</style>
