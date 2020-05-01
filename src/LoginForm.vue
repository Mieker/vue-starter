<template>
  <div>
    <label>Zaloguj sie e-mailem</label>
    <input type="email" v-model="email" text="sad"/>
    <button @click="enter()">{{buttonLabelToDisplay}}</button>
  </div>
</template>

<script>
export default {
  props: ['logInButtonLabel'],
  data() {
    return {
      email: ""
    };
  },
  methods: {
    enter() {
      this.$emit("login", this.email);
    }
  },
  computed: {
	  buttonLabelToDisplay() {
		  return this.logInButtonLabel || 'Zaloguj sie';
	  }
  }
};
</script>