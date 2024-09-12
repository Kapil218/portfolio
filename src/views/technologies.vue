<template>
  <v-row
    justify="center"
    align="center"
    :style="{ padding: isMobile ? '4rem 12px' : '4rem' }"
  >
    <v-col
      cols="12"
      class="text-center text-h4 mb-4"
      style="color: rgb(204, 204, 1)"
    >
      I'm Working on</v-col
    >
    <v-col
      cols="10"
      class="mb-4"
      style="color: rgb(218, 208, 208); word-spacing: 3px"
    >
    Adopting a straightforward and uncomplicated approach to life, while still holding onto ambitious aspirations, forms the core of my personal philosophy. I believe that simplicity allows for greater focus and clarity, helping to navigate the complexities of life without unnecessary distractions. This approach keeps me grounded, yet it doesn't diminish my drive to aim high and reach for my goals. With this mindset, I am able to pursue my objectives with determination, balancing practicality with vision, and consistently working towards making my aspirations a reality.</v-col
    >
<v-col   cols="12"></v-col>
    <v-col
      md="2"
      cols="6"
      sm="4"
      v-for="(item, i) in technologies"
      :key="i"
      class="text-center"
    >
      <v-tooltip bottom>
        <template v-slot:activator="{ on, attrs }">
          <v-avatar class="ma-4 logo" size="100" v-bind="attrs" v-on="on">
            <v-img
              style="max-width: 100%; max-height: 100%"
              :src="item.src"
              alt="Avatar"
              contain
            />
          </v-avatar>
        </template>
        <span class="text-h6">{{ item.name }}</span>
      </v-tooltip>
    </v-col>
  </v-row>
</template>

<script>
export default {
  data() {
    return {
      technologies: [
        { name: "Vue", src: require("../assets/vue.svg") },
        { name: "Vuetify", src: require("../assets/vuetify.svg") },
        { name: "HTML", src: require("../assets/html.svg") },
        { name: "CSS", src: require("../assets/css.svg") },
        { name: "JS", src: require("../assets/js.svg") },
        { name: "React", src: require("../assets/react.png") },
        { name: "Express", src: require("../assets/express.png") },
        { name: "MongoDb", src: require("../assets/mongodb.svg") },
        { name: "NodeJs", src: require("../assets/nodejs.svg") },
        { name: "Bootstrap", src: require("../assets/bootstrap.svg") },
        { name: "Github", src: require("../assets/github.png") },
        { name: "MySql", src: require("../assets/mysql-official.svg") },
        { name: "Tailwind", src: require("../assets/tailwindcss.svg") },
        { name: "Docker", src: require("../assets/docker-svgrepo-com.svg") },

      ],
    };
  },
  computed: {
    isMobile() {
      return this.$vuetify.breakpoint.xsOnly;
    },
  },
};
</script>

<style scoped>
.logo {
  transition: transform 0.2s ease;
}
.logo:hover {
  transform: scale(1.2);
}
</style>
