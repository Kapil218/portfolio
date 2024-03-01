<template>
  <v-row justify="center" align="center" style="padding: 4rem">
    <v-col
      cols="12"
      class="text-center text-h4 mb-4"
      style="color: rgb(204, 204, 1)"
    >
      I'm Working on</v-col
    >
    <v-col
      cols="12"
      class="mb-4"
      style="color: rgb(218, 208, 208); word-spacing: 5px"
      >I strongly value thinking creatively and outside the conventional
      boundaries. I also believe that learning is a continuous process that
      persists throughout one's life, regardless of age. Adopting a
      straightforward and uncomplicated approach to life, while still
      maintaining ambitious aspirations, is my philosophy. With this mindset, I
      am actively pursuing my objectives.</v-col
    >

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
      ],
    };
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
