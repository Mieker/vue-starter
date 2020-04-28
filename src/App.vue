<template>
	<div>
    	<h1>System do zapisów na zajęcia</h1>

		<div v-if="authenticatedUsername">
			<greeting-form :user="authenticatedUsername" @login="logMeOut()"></greeting-form>
		</div>
    	<div v-else>
      		<login-form @login="logMeIn($event)"></login-form>
    	</div>
  	</div>
</template>

<script>
import "milligram";
import LoginForm from "./LoginForm";
import GreetingForm from "./GreetingForm";

export default {
  components: { LoginForm, GreetingForm },
  data() {
    return {
      authenticatedUsername: ""
    };
  },

  methods: {
    logMeIn(username) {
      this.authenticatedUsername = username;
    },
    logMeOut() {
      this.authenticatedUsername = "";
    }
  }
};
</script>

<style>
</style>
