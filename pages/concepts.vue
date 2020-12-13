<template>
  <v-sheet class="mt-2 pt-2" color="white">
    <v-row>
      <v-col offset="4" cols="4">
        <v-autocomplete
          v-model="active_subject"
          solo
          :items="subjects"
          label="Select a subject"
        ></v-autocomplete>
      </v-col>
      <v-col cols="1">
        <v-btn fab small color="warning">
          <v-icon dark>mdi-plus</v-icon>
        </v-btn>
      </v-col>
    </v-row>
    <v-row>
      <!-- <v-data-table
        headers="headers"
        items="items"
        hide-actions
        class="elevation-1"
        select-all
        pagination.sync="pagination"
        item-key="id"
        loading="true"
        search="search"
      >

      </v-data-table> -->
    </v-row>
  </v-sheet>
</template>

<script>
export default {
  data() {
    return {
      subjects: ['Chemistry - 12th', 'Physics - 11th', 'Mathematics - 12th'],
      active_subject: null,
    }
  },
}
</script>

<style>
.mdi-menu-down {
  cursor: pointer;
}
</style>
