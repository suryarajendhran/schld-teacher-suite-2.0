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
          <v-btn dark color="black">students</v-btn>
          <v-btn color="orange">Confidence</v-btn>
          <v-btn color="yellow">Activity</v-btn>
          <v-spacer></v-spacer>
        </v-card-actions>
      </v-card>
    </v-row>
    <v-row>
      <!-- <v-card class="mt-4 mx-auto" elevation="12" max-width="calc(100%-32px)"> -->
      <v-sparkline
        :value="value"
        :gradient="gradient"
        :smooth="radius || false"
        :padding="padding"
        :line-width="width"
        :stroke-linecap="lineCap"
        :gradient-direction="gradientDirection"
        :fill="fill"
        :type="type"
        :auto-line-width="autoLineWidth"
        auto-draw
      ></v-sparkline>
      <!-- </v-card> -->
    </v-row>
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
      width: 2,
      radius: 10,
      padding: 8,
      lineCap: 'round',
      gradient: gradients[5],
      value: [0, 2, 5, 9, 5, 10, 3, 5, 0, 0, 1, 8, 2, 9, 0],
      gradientDirection: 'top',
      gradients,
      fill: false,
      type: 'trend',
      autoLineWidth: false,
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
        { label: '15th', questions: '122' },
        { label: '16th', questions: '99' },
        { label: '17th', questions: '117' },
      ],
    }
  },
  computed: {
    // labels() {
    //   let labels = []
    //   if (this.activity) {
    //     this.activity.forEach((day) => {
    //       labels.push(day.label)
    //     })
    //   }
    //   return labels
    // },
    // value() {
    //   let values = []
    //   if (this.activity) {
    //     this.activity.forEach((day) => {
    //       values.push(parseInt(day.questions))
    //     })
    //   }
    //   return values
    // },
  },
}
</script>
