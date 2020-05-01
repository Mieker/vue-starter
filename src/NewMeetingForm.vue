<template>
<form @submit.prevent="addNewMeeting()">
	<h3>Dodaj nowe spotkanie</h3>
	<label>Nazwa</label> <input type="text" v-model="newMeeting.name">
	<label>Opis</label>
	<textarea v-model="newMeeting.description"></textarea>
	<!-- <button>Dodaj</button> -->
	<input id="inputButton" type="submit" value="Dodaj">
	<div id="errorText" v-if="submitError">Spotkanie musi mieć nazwę!</div>
</form>
</template>

<script>
export default {
	data() {
      return {
          newMeeting: {},
          submitError: false
      };
  },
  	methods: {
      addNewMeeting() {
    	  if (this.newMeeting.name) {
    	  	this.$emit('added', this.newMeeting);
	        this.newMeeting = {};
    	  }
    	  else {
    		  this.submitError = true;
    	  }
      },
	},
}
</script>

<style>
	#errorText {
		display: inline;
		color: red;
		margin-left: 10px;
	}
</style>