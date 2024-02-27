<template>
  <v-app>
    <v-app-bar class="gg2" app color="#455A64" dark>
      <div class="d-flex align-center">
        <v-btn rounded x-large text to="/"
          ><span style="font-family: cursive" class="grey--text mr-2"
            >Portfolio</span
          >
          <span style="font-family: cursive">KSR</span>
        </v-btn>
      </div>
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
</style>
