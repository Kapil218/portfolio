<template>
  <v-row justify="center" align="center" style="margin-top: 12rem">
    <v-col cols="12" class="text-center white--text text-h2"
      >Web Technologies</v-col
    >
    <v-col
      md="2"
      cols="3"
      sm="4"
      v-for="(item, i) in technologies"
      :key="i"
      class="text-center"
    >
      <v-avatar class="mx-2" size="150">
        <v-img
          style="max-width: 100%; max-height: 100%"
          :src="item.src"
          alt="Avatar"
          contain
        />
      </v-avatar>
      <p class="text-h5" style="color: rgb(0, 217, 255)">{{ item.name }}</p>
    </v-col>
  </v-row>
</template>

<script>
export default {
  data() {
    return {
      technologies: [
        { name: "Vue", src: require("../assets/vue.png") },
        { name: "Vuetify", src: require("../assets/vuetify.png") },
        { name: "HTML", src: require("../assets/html.png") },
        { name: "CSS", src: require("../assets/css.png") },
        { name: "React", src: require("../assets/react.png") },
        { name: "Express", src: require("../assets/express.png") },
        { name: "MongoDb", src: require("../assets/mongodb.png") },
        { name: "NodeJs", src: require("../assets/nodejs.png") },
        { name: "Bootstrap", src: require("../assets/bootstrap.png") },
      ],
    };
  },
};
</script>

<style scoped></style>
