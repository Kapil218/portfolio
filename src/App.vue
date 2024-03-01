<template>
  <v-app>
    <v-app-bar class="gg2" app color="#455A64" dark>
      <div class="d-flex align-center">
        <v-btn class="nav" rounded x-large text to="/"
          ><span style="font-family: cursive" class="grey--text mr-2"
            >Portfolio</span
          >
          <span style="font-family: cursive">KSR</span>
        </v-btn>
      </div>
      <v-spacer> </v-spacer>
      <v-btn
        class="nav mr-2"
        style="color: rgb(92, 181, 94)"
        href="#technologies"
        >technologies</v-btn
      >
      <v-btn
        class="nav mr-2"
        style="color: rgb(22, 223, 234)"
        href="#experience"
        >experience</v-btn
      >
      <v-btn class="nav mr-2" style="color: rgb(204, 204, 1)" href="#resume"
        >resume</v-btn
      >
      <v-btn class="nav mr-2" style="color: rgb(209, 42, 209)" href="#connect"
        >connect</v-btn
      >
    </v-app-bar>

    <v-main>
      <router-view />
    </v-main>
    <v-footer class="d-flex flex-column">
      <div class="px-4 py-2 bg-black text-center w-100">
        {{ new Date().getFullYear() }} — <strong>Kapil Singh Rathore</strong>
      </div>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: "App",

  data: () => ({}),
};
</script>
<style scoped>
.gg2 {
  /* Fallback color */
  background-color: #000000;

  /* Gradient */
  background-image: linear-gradient(to bottom right, #000000, #262e30);
}
.nav {
  animation: loading-nav 2s ease-out 1s;
}
@keyframes loading-nav {
  0% {
    opacity: 0.1;
    transform: translateX(1000%);
  }
  50% {
    opacity: 0.2;
    transform: translateX(1000%);
  }
  100% {
    opacity: 1;
    transform: translateX(0%);
  }
}
</style>
