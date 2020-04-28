<template>
 	<div>
		<h3 id="welcome">Witaj {{user}}!</h3>
		<button id="logOutButton" class="button button-outline" @click="getOut()">{{buttonLabelToDisplay}}</button>
  	</div>
</template>

<script>
	export default {
		props: ['user', 'logOutButtonLabel'],
		methods: {
		    getOut() {
		      this.$emit("login");
		    }
		},
		computed: {
			  buttonLabelToDisplay() {
				  return this.logOutButtonLabel || 'Wyloguj';
			  }
		}
	};
</script>

<style>
	#welcome {
		display: inline;
	}
	#logOutButton {
		display: inline;
		float: right;
	}
</style>