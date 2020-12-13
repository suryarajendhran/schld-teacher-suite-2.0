<template>
  <v-col>
    <v-row justify="space-between">
      <v-card class="mt-2" v-for="room in classes" :key="room.cid" width="380">
        <v-card-title primary-title cl>
          <div>
            <div class="headline">{{ room.grade }} - {{ room.section }}</div>
            <span class="lighten-2">{{ room.group }} - {{ room.subject }}</span>
          </div>
        </v-card-title>
        <v-card-text>
          <div class="text--lighten-1">
            Number of students: {{ room.student_count }}
          </div>
        </v-card-text>
        <v-card-actions>
          <v-btn dark color="black" @click="openStudentDialog(room)"
            >students</v-btn
          >
          <v-btn color="orange">Confidence</v-btn>
          <v-btn color="yellow">Activity</v-btn>
          <v-spacer></v-spacer>
        </v-card-actions>
      </v-card>
    </v-row>
    <div>
      <v-card
        class="mt-6 pb-2 mx-auto"
        elevation="2"
        max-width="calc(100%-32px)"
      >
        <v-sparkline
          :value="value"
          :labels="labels"
          label-size="5"
          line-width="2"
          color="#555"
          height="100"
          padding="24"
          stroke-linecap="round"
          smooth
        >
        </v-sparkline>
      </v-card>

      <!-- Student Dialog Start -->
      <StudentDialog
        :dialog="studentDialog"
        :room="studentDialogOpenClass"
        @close="studentDialog = false"
      />
      <!-- Student Dialog End -->
    </div>
  </v-col>
</template>

<script>
export default {
  data() {
    const gradients = [
      ['#222'],
      ['#42b3f4'],
      ['red', 'orange', 'yellow'],
      ['purple', 'violet'],
      ['#00c6ff', '#F0F', '#FF0'],
      ['#f72047', '#ffd200', '#1feaea'],
    ]
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
      activity: [
        { label: '12th', questions: '120' },
        { label: '13th', questions: '104' },
        { label: '14th', questions: '144' },
        { label: '15th', questions: '102' },
        { label: '16th', questions: '99' },
        { label: '17th', questions: '117' },
      ],
      studentDialog: false,
      studentDialogOpenClass: null,
    }
  },
  methods: {
    openStudentDialog(room) {
      this.studentDialog = true
      this.studentDialogOpenClass = room
    },
  },
  computed: {
    labels() {
      let labels = []
      if (this.activity) {
        this.activity.forEach((day) => {
          labels.push(day.label)
        })
      }
      return labels
    },
    value() {
      let values = []
      if (this.activity) {
        this.activity.forEach((day) => {
          values.push(parseInt(day.questions))
        })
      }
      return values
    },
  },
}
</script>
