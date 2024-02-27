<template>
  <v-row class="white rounded-xl">
    <v-col cols="12">
      <v-form ref="form" v-model="valid">
        <v-container>
          <span class="grey--text" style="font-size: 1.5rem">Let's Talk</span>

          <v-row>
            <v-col cols="12">
              <v-text-field
                v-model="firstname"
                label="First name"
                required
              ></v-text-field>
            </v-col>

            <v-col cols="12">
              <v-text-field
                v-model="lastname"
                label="Last name"
                required
              ></v-text-field>
            </v-col>

            <v-col cols="12">
              <v-text-field
                v-model="email"
                label="E-mail"
                required
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
              ></v-text-field>
            </v-col>
          </v-row>
          <v-btn class="mr-4" @click="submit"> submit </v-btn>
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
    //
    email: "",
    //
    message: "",
  }),
  methods: {
    submit() {
      console.log(this.firstname, this.lastname, this.email, this.message);
      this.$refs.form.reset();
    },
  },
};
</script>

<style scoped></style>
