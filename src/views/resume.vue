<template>
  <v-row
    justify="center"
    align="center"
    :style="{ padding: isMobile ? '4rem 12px' : '4rem' }"
  >
    <v-col cols="12" class="text-h4 mb-4" style="color: rgb(92, 181, 94)">
      Academics & CV
    </v-col>
    <v-col cols="12" md="4" sm="12">
      <v-card class="black pa-3">
        <h2 class="purple--text mb-4">For More...</h2>
        <p class="text-center">
          <v-btn outlined color="yellow" href="https://drive.google.com/uc?export=download&id=106u-SNNZ30nNg4OBuHL069R0LVB6ABO1">
            Download CV
          </v-btn>
        </p>
      </v-card>
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
