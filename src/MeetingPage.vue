<template>
<div>
	<button v-show="!isAddButtonClicked" @click="isAddButtonClicked=true">{{buttonLabelToDisplay}}</button>
	<new-meeting-form v-show="isAddButtonClicked" @added="addNewMeeting($event)"></new-meeting-form>
	<meetings-list :meetings="meetings" :username="username"></meetings-list>
</div>
</template>

<script>
import NewMeetingForm from "./NewMeetingForm";
import MeetingsList from "./MeetingsList";

export default {
  	props: ['addNewMeetingButtonLabel', 'username'],
	components: {NewMeetingForm, MeetingsList},
  data() {
      return {
          meetings: [],
          isAddButtonClicked: false,
      };
  },
  methods: {
      addNewMeeting(meeting) {
          this.meetings.push(meeting);
    	  this.isAddButtonClicked = false;
      },
  },
  computed: {
	  buttonLabelToDisplay() {
		  return this.addNewMeetingButtonLabel || 'Dodaj nowe spotkanie';
	  }
  }
}
</script>