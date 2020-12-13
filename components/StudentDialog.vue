<template>
  <v-dialog
    v-model="dialog"
    fullscreen
    hide-overlay
    transition="dialog-bottom-transition"
  >
    <v-card>
      <v-toolbar dark color="black">
        <v-btn icon dark @click="$emit('close')">
          <v-icon>mdi-close</v-icon>
        </v-btn>
        <v-toolbar-title>Students</v-toolbar-title>
        <v-spacer></v-spacer>
      </v-toolbar>
      <v-banner elevation="0.5">
        <h2 is-center>{{ room.grade }} - {{ room.section }} {{room.subject}}</h2>
      </v-banner>
      <v-data-table
      :headers="headers"
      :items="students"
      :items-per-page="40"
      class="elevation-1"
    ></v-data-table>
    </v-card>
  </v-dialog>
</template>

<script>
export default {
  props: ['dialog', 'room'],
  data() {
    return {
      headers: [
        {
          text: 'Student',
          align: 'start',
          sortable: false,
          value: 'name',
        },
        { text: 'Email', value: 'email' },
        { text: 'Status', value: 'status' },
        { text: 'Last Active', value: 'active' },
      ],
      students: [
        {
          name: 'Jason Bourne',
          email: 'jason@bourne.com',
          status: '50%',
          active: 'Two Days Ago',
        },
        {
          name: 'James Bond',
          email: 'james007@bond.com',
          status: '70%',
          active: '1 Hour Ago',
        },
        {
          name: 'Jack Sparrow',
          email: 'jack@blackpearl.com',
          status: '20%',
          active: '5 minutes Ago',
        },
        {
          name: 'Johny English',
          email: 'johnnyenglish@toshibami6.com',
          status: '100%',
          active: '12-12-2020 8:00 PM',
        },
      ],
    }
  },
}
</script>

<style>
</style>