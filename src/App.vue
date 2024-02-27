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

      <v-spacer></v-spacer>

      <span
        class="white--text mr-2"
        style="font-size: 1.2rem; font-family: cursive"
      >
        FOLLOW ME@
      </span>
      <v-btn
        v-for="(icon, i) in icons"
        :key="i"
        class="mx-2 my-4 white--text icon"
        icon
        :href="icon.link"
        target="_blank"
      >
        <v-icon size="50px">
          {{ icon.icon }}
        </v-icon>
      </v-btn>
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

  data: () => ({
    icons: [
      { icon: "mdi-github", link: "https://github.com/Kapil218" },

      {
        icon: "mdi-linkedin",
        link: "https://www.linkedin.com/in/kapil-singh-rathore-42443a22a/",
      },
      {
        icon: "mdi-instagram",
        link: "https://www.instagram.com/kapil.singhrathore/",
      },
      {
        icon: "mdi-gmail",
        link: "https://mail.google.com/mail/?view=cm&fs=1&to=kapilsinghrathore218@gmail.com",
      },
    ],
  }),
};
</script>
<style scoped>
.gg2 {
  /* Fallback color */
  background-color: #000000;

  /* Gradient */
  background-image: linear-gradient(to bottom right, #000000, #262e30);
}
.icon:hover {
  box-shadow: 0 0 5px #fffffe;
}
</style>
