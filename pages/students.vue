<template>
  <v-row class="my-2 mx-2">
    <v-card elevation="2" width="250">
      <v-card-title>12th/CB/Business Studies</v-card-title>
      <v-card-text
        >25 students and counting. Just began onboarding.</v-card-text
      >
      <v-divider class="mx-4"></v-divider>
      <v-card-actions>
        <v-btn color="deep-purple" text @click="reserve"> View students </v-btn>
      </v-card-actions>
    </v-card>
    <v-spacer></v-spacer>
    <v-card elevation="2" width="250">
      <v-card-title>12th/CA/Economics</v-card-title>
      <v-card-text>120 tests yesterday and on schedule.</v-card-text>
      <v-divider class="mx-4"></v-divider>
      <v-card-actions>
        <v-btn color="deep-purple lighten-2" text @click="reserve">
          View students
        </v-btn>
      </v-card-actions>
    </v-card>
    <v-spacer></v-spacer>
    <v-card elevation="2" width="250">
      <v-card-title>12th/CA/Business Studies</v-card-title>
      <v-card-text>22% lower tests today. Need attention!</v-card-text>
      <v-divider class="mx-4"></v-divider>
      <v-card-actions>
        <v-btn color="deep-purple lighten-2" text @click="reserve">
          View students
        </v-btn>
      </v-card-actions>
    </v-card>
    <v-spacer></v-spacer>
  </v-row>
</template>

<script>
export default {}
</script>

<style></style>
