<template>
    <div>
    <div v-show="meetings.length > 0">
    <h4>Zaplanowane zajecia ({{meetings.length}})</h4>
    <table>
        <thead>
            <tr>
                <th class="nameCol">Nazwa spotkania</th>
                <th class="descriptionCol">Opis</th>
                <th class="membersCol">Uczestnicy</th>
            </tr>
        </thead>
        <tbody>
            <tr v-for="meeting in meetings" :key="meeting.name">
                <td class="nameCol">{{ meeting.name }}</td>
                <td class="descriptionCol">{{ meeting.description }}</td>
                <td class="membersCol"><meeting-enroller :username="username" :meetingID="meetings.indexOf(meeting)" @deleteMeeting="deleteMeeting($event)"></meeting-enroller></td>
            </tr>
        </tbody>
    </table>
    </div>
    <div v-if="meetings.length <= 0">
    	<p>Brak zaplanowanych spotkan.</p>
    </div>
    </div>
</template>

<script>
import MeetingEnroller from "./MeetingEnroller";

export default {
    props: ['meetings', 'username'],
    components: {MeetingEnroller},
    methods: {
	      deleteMeeting(metNum) {
	    	 this.meetings.splice(metNum, 1);
	      },
	}
}
</script>

<style>
	.nameCol {
		width: 15%
	}
	.descriptionCol {
		width: 30%
	}
	.membersCol {
		width: 55%;
	}
</style>