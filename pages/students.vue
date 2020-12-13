<template>
  <v-row class="my-2 mx-2">
    <v-card elevation="2" width="290">
      <v-card-title>12th/CB/Business Studies</v-card-title>
      <v-card-text
        >Total Number of students: 20</v-card-text
      >
      <v-divider class="mx-4"></v-divider>
      <v-card-actions>
        <v-btn color="deep-purple" text @click="reserve"> View students </v-btn>
      </v-card-actions>
    </v-card>
    <v-spacer></v-spacer>
    <v-card elevation="2" width="290">
      <v-card-title>12th/CA/Economics</v-card-title>
      <v-card-text>Total Number of students: 18</v-card-text>
      <v-divider class="mx-4"></v-divider>
      <v-card-actions>
        <v-btn color="deep-purple" text @click="reserve">
          View students
        </v-btn>
      </v-card-actions>
    </v-card>
    <v-spacer></v-spacer>
    <v-card elevation="2" width="290">
      <v-card-title>12th/CA/Business Studies</v-card-title>
      <v-card-text>Total Number of students: 10</v-card-text>
      <v-divider class="mx-4"></v-divider>
      <v-card-actions>
        <v-btn color="deep-purple" text @click="reserve">
          View students
        </v-btn>
      </v-card-actions>
    </v-card>
    <v-spacer></v-spacer>
  </v-row>
</template>

<script>
export default {
  data() {
    return {
    }
  }
}
</script>

<style></style>
