<template>
  <v-container fluid class="black gg" style="height: 100%">
    <heroVue id="hero" />
    <hr />
    <technologiesVue id="technologies" class="loading" />
    <hr />
    <experienceVue id="experience" class="loading" />
    <hr />
    <resumeVue id="resume" class="loading" />
    <hr />
    <connectVue id="connect" class="loading" />
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
.loading {
  animation: loading 900ms linear 2s;
}
@keyframes loading {
  0% {
    opacity: 0.1;
    transform: translateX(100%);
  }
  33% {
    opacity: 0.3;
    transform: translateX(66%);
  }
  66% {
    opacity: 0.6;
    transform: translateX(33%);
  }
  100% {
    opacity: 1;
    transform: translateX(0%);
  }
}
.gg {
  /* Fallback color */
  background-color: #000000;

  /* Gradient */
  background-image: linear-gradient(to bottom right, #0f1010, #0e0d0e);
}
</style>
