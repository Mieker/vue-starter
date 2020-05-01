<template>
	<div>
    	<h1>System do zapisów na zajęcia</h1>

		<div v-show="authenticatedUsername">
			<greeting :user="authenticatedUsername" @login="logMeOut()"></greeting></br>
			<meeting-page></meeting-page>
		</div>
    	<div v-if="!authenticatedUsername">
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
