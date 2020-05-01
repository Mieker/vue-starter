<template>
    <div>
    <div v-show="meetings.length > 0">
    <h4>Zaplanowane zajęcia ({{meetings.length}})</h4>
    <table>
        <thead>
            <tr>
                <th>Nazwa spotkania</th>
                <th>Opis</th>
                <th>Uczestnicy</th>
                <th></th>
            </tr>
        </thead>
        <tbody>
            <tr v-for="meeting in meetings" :key="meeting.name">
                <td >{{ meeting.name }}</td>
                <td>{{ meeting.description }}</td>
                <td><meeting-enroller :username="username"></meeting-enroller></td>
            </tr>
        </tbody>
    </table>
    </div>
    <div v-if="meetings.length <= 0">
    	<p>Brak zaplanowanych spotkań.</p>
    </div>
    </div>
</template>

<script>
import MeetingEnroller from "./MeetingEnroller";

export default {
    props: ['meetings', 'username'],
    components: {MeetingEnroller},
    
}
</script>