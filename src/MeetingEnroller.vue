<template>
	<div>
	<ul>
		<li v-for="user in users">{{ user }} 
		</li>
	</ul>
		<div id="enrollerButtons">
			<button class="button button-outline" v-if="!isUsersContains()" @click="addUser()">Zapisz sie</button>
			<button v-if="this.users.length <= 0" @click="$emit('deleteMeeting', meetingID)">Usun puste spotkanie</button>
			<button class="button button-outline" v-if="isUsersContains()" @click="removeUser()">Wypisz sie</button>
		</div>
	</div>
</template>

<script>
export default {
	props: ['username', 'meetingID'],
	data() {
	      return {
	          users: [],
	      };
	},
	methods: {
	      isUsersContains() {
	    	  return this.users.includes(this.username);
	      },
	      addUser() {
	    	  this.users.push(this.username);
	      },
	      removeUser() {
				var index = this.users.indexOf(this.username);
				this.users.splice(index, 1);
	      }
	}
}
</script>

<style>
	#enrollerButtons {
		display: inline;
		float: right;
	}
	ul {
		float: left;
	}
	button {
		margin-right : 10px;
	}
</style>