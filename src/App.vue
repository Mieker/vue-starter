<template>
	<div>
    	<h1>System do zapisów na zajęcia</h1>

		<div v-if="authenticatedUsername">
			<greeting :user="authenticatedUsername" @login="logMeOut()"></greeting>
			<meeting-page></meeting-page>
		</div>
    	<div v-else>
      		<login-form @login="logMeIn($event)"></login-form>
    	</div>
  	</div>
</template>

<script>
import "milligram";
import LoginForm from "./LoginForm";
import Greeting from "./Greeting";
import MeetingPage from "./MeetingPage";

export default {
  components: { LoginForm, Greeting, MeetingPage },
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
