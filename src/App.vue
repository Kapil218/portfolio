<template>
  <v-app>
    <!-- App bar for mobile -->
    <v-navigation-drawer v-model="drawer" class="black" app temporary>
      <!-- Mobile navigation items -->
      <v-list>
        <v-list-item
          v-for="(item, index) in navItems"
          :key="index"
          class="pa-0"
          link
          @click="
            goToSection(item.href);
            drawer = false;
          "
        >
          <v-list-item-title
            class="grey--text pa-6"
            style="border-bottom: 1px solid grey"
            >{{ item.text }}</v-list-item-title
          >
        </v-list-item>
      </v-list>
      <!-- Hamburger icon to close the drawer -->
      <v-btn icon @click="drawer = false">
        <v-icon>mdi-close</v-icon>
      </v-btn>
    </v-navigation-drawer>

    <!-- App bar for tablet and larger screens -->
    <v-app-bar app color="#455A64" dark>
      <v-btn icon @click.stop="drawer = !drawer">
        <v-icon>mdi-menu</v-icon>
      </v-btn>
      <v-btn href="#hero" class="nav" rounded x-large text>
        <span style="font-family: cursive" class="grey--text mr-2"
          >Portfolio</span
        >
        <span style="font-family: cursive">KSR</span>
      </v-btn>
      <v-spacer></v-spacer>
      <!-- Desktop navigation items -->
      <p v-if="!isSmallScreen" class="ma-0">
        <v-btn
          v-for="(item, index) in navItems"
          :key="index"
          class="nav mr-2"
          :style="{ color: item.color }"
          :href="item.href"
        >
          {{ item.text }}
        </v-btn>
      </p>
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
    drawer: false,
    navItems: [
      {
        text: "Technologies",
        href: "#technologies",
        color: "rgb(92, 181, 94)",
      },
      { text: "Experience", href: "#experience", color: "rgb(22, 223, 234)" },
      { text: "Resume", href: "#resume", color: "rgb(204, 204, 1)" },
      { text: "Connect", href: "#connect", color: "rgb(209, 42, 209)" },
    ],
  }),
  computed: {
    isSmallScreen() {
      return this.$vuetify.breakpoint.smAndDown;
    },
  },
  methods: {
    goToSection(href) {
      // Method to scroll to the selected section
      document.querySelector(href).scrollIntoView({ behavior: "smooth" });
    },
  },
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
