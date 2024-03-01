<template>
  <v-row
    justify="center"
    align="center"
    :style="{ padding: isMobile ? '4rem 12px' : '4rem' }"
  >
    <v-col cols="12" class="text-h4 mb-4" style="color: rgb(92, 181, 94)">
      Experience</v-col
    >
    <v-col cols="12">
      <template>
        <v-card class="mx-auto" max-width="400" outlined>
          <v-list-item three-line>
            <v-list-item-content>
              <div class="text-overline mb-4">DECEMBER 2022 - Present</div>
              <v-list-item-title class="text-h5 mb-1">
                Web Developer Intern
              </v-list-item-title>
              <v-list-item-subtitle>agprop</v-list-item-subtitle>
            </v-list-item-content>

            <v-avatar size="80" color="grey"
              ><v-img src="../assets/agprop.png"></v-img
            ></v-avatar>
          </v-list-item>

          <v-card-actions class="d-flex justify-center">
            <v-btn href="https://agprop.in/" outlined color="teal" rounded text>
              Company Website
            </v-btn>
          </v-card-actions>
        </v-card>
      </template>
    </v-col>
  </v-row>
</template>

<script>
export default {
  data() {
    return {};
  },
  computed: {
    isMobile() {
      return this.$vuetify.breakpoint.xsOnly;
    },
  },
};
</script>

<style scoped></style>
