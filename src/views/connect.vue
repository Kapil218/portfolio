<template>
  <v-row justify="center" align="center" :style="{ padding: isMobile ? '4rem 12px' : '4rem' }">
    <v-col cols="12" class="text-h4 mb-4" style="color: rgb(92, 181, 94)">
      Let's Connect
    </v-col>

    <v-col cols="12" sm="8">
      <v-form ref="form" v-model="valid">
        <v-container>
          <v-row>
            <v-col cols="12">
              <v-text-field v-model="firstname" label="First name" required dark></v-text-field>
            </v-col>

            <v-col cols="12">
              <v-text-field v-model="lastname" label="Last name" required dark></v-text-field>
            </v-col>

            <v-col cols="12">
              <v-text-field v-model="email" label="E-mail" required dark></v-text-field>
            </v-col>
          </v-row>

          <v-row>
            <v-col cols="12">
              <v-text-field v-model="message" label="Topic" outlined clearable dark></v-text-field>
            </v-col>
          </v-row>

          <v-row justify="center">
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
import emailjs from 'emailjs-com';

// Initialize EmailJS with your User ID
emailjs.init('masDsvNdMIesnhmUS');  // Replace 'YOUR_USER_ID' with your actual EmailJS User ID

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
      const templateParams = {
        firstname: this.firstname,
        lastname: this.lastname,
        email: this.email,
        message: this.message,
        to_name: 'Kapil',
      };

      emailjs.send('resume-mail-template', 'resume-mail-template', templateParams) // Replace these with your actual IDs
        .then((response) => {
          console.log('SUCCESS!', response.status, response.text);
          alert('Your message has been sent!');
          this.$refs.form.reset();
        }, (error) => {
          console.log('FAILED...', error);
          alert('Failed to send the message. Please try again later.');
        });
    },
  },
};
</script>

<style scoped>
/* Add custom styles if needed */
</style>
