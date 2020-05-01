<template>
	<div>
	<ul>
		<li v-for="user in users">{{ user }} 
		</li>
	</ul>
		<div id="enrollerButtons">
			<button class="button button-outline" v-if="!isUsersContains()">Zapisz się</button>
			<button v-if="this.users.length <= 0">Usuń puste spotkanie</button>
			<button class="button button-outline" v-if="isUsersContains()">Wypisz się</button>
		</div>
	</div>
</template>

<script>
export default {
	props: ['username'],
	data() {
	      return {
	          users: ["user1", "user2"],
	      };
	},
	methods: {
	      isUsersContains() {
	    	  return this.users.includes("user1");
	      },
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