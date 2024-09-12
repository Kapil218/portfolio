<template>
  <v-container fluid class="black gg" style="height: 100%">
    <heroVue id="hero" />
    <hr />
    <technologiesVue id="technologies"   />
    <hr />
    <experienceVue id="experience"   />
    <hr />
    <resumeVue id="resume"   />
    <hr />
    <connectVue id="connect"   />
  </v-container>
</template>

<script>
import connectVue from "./connect.vue";
import experienceVue from "./experience.vue";
import technologiesVue from "./technologies.vue";
import resumeVue from "./resume.vue";
import heroVue from "./hero.vue";
export default {
  name: "Home",
  components: {
    connectVue,
    technologiesVue,
    experienceVue,
    resumeVue,
    heroVue,
  },
  data() {
    return {};
  },
};
</script>

<style scoped>

.gg {
  /* Fallback color */
  background-color: #000000;

  /* Gradient */
  background-image: linear-gradient(to bottom right, #0f1010, #0e0d0e);
}
</style>
