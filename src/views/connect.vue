<template>
  <v-row class="gg2" justify="center">
    <v-col cols="8">
      <v-form ref="form" v-model="valid">
        <v-container>
          <span class="white--text" style="font-size: 1.5rem">Let's Talk</span>

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

<style scoped>
.gg2 {
  /* Gradient */
  background: linear-gradient(to bottom right, #00c3fe, #91b4bd);
}
</style>
