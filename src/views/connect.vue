<template>
  <v-row
    justify="center"
    align="center"
    :style="{ padding: isMobile ? '4rem 12px' : '4rem' }"
  >
    <v-col cols="12" class="text-h4 mb-4" style="color: rgb(92, 181, 94)">
      Let's Connect
    </v-col>

    <v-col cols="12" sm="8">
      <!-- Added sm="8" for small screens -->
      <v-form ref="form" v-model="valid">
        <v-container>
          <v-row>
            <v-col cols="12">
              <v-text-field
                v-model="firstname"
                label="First name"
                required
                dark
              ></v-text-field>
            </v-col>

            <v-col cols="12">
              <v-text-field
                v-model="lastname"
                label="Last name"
                required
                dark
              ></v-text-field>
            </v-col>

            <v-col cols="12">
              <v-text-field
                v-model="email"
                label="E-mail"
                required
                dark
              ></v-text-field>
            </v-col>
          </v-row>

          <v-row>
            <v-col cols="12">
              <v-text-field
                v-model="message"
                label="Topic"
                outlined
                clearable
                dark
              ></v-text-field>
            </v-col>
          </v-row>

          <v-row justify="center">
            <!-- Center the button -->
            <v-col cols="12">
              <v-btn @click="submit" color="primary">Submit</v-btn>
            </v-col>
          </v-row>
        </v-container>
      </v-form>
    </v-col>
  </v-row>
</template>

<script>
export default {
  data: () => ({
    valid: false,
    firstname: "",
    lastname: "",
    email: "",
    message: "",
  }),
  computed: {
    isMobile() {
      return this.$vuetify.breakpoint.xsOnly;
    },
  },
  methods: {
    submit() {
      console.log(this.firstname, this.lastname, this.email, this.message);
      this.$refs.form.reset();
    },
  },
};
</script>

<style scoped>
/* Add custom styles if needed */
</style>
