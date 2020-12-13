<template>
  <v-row justify="space-between">
    <v-card class="mt-2" v-for="room in classes" :key="room.cid" width="380">
      <v-card-title primary-title>
        <div>
          <div class="headline">{{ room.grade }} - {{ room.section }}</div>
          <span class="lighten-2">{{ room.group }}</span>
        </div>
      </v-card-title>
      <v-card-text>
        <div class="text--lighten-1">
          Number of students: {{ room.student_count }}
        </div>
      </v-card-text>
      <v-card-actions>
        <v-btn dark color="black">students</v-btn>
        <v-btn color="orange">Confidence</v-btn>
        <v-btn color="yellow">Activity</v-btn>
        <v-spacer></v-spacer>
      </v-card-actions>
    </v-card>
  </v-row>
</template>

<script>
export default {
  data() {
    return {
      classes: [
        {
          cid: '18474uy',
          subject: 'Business Studies',
          grade: '12',
          section: 'B',
          group: 'Commerce',
          student_count: 12,
        },
        {
          cid: 'u134yi4uy',
          subject: 'Economics',
          grade: '12',
          section: 'A',
          group: 'Commerce',
          student_count: 22,
        },
        {
          cid: '10pow2ii',
          subject: 'Economics',
          grade: '12',
          section: 'B',
          group: 'Commerce',
          student_count: 22,
        },
      ],
    }
  },
}
</script>
