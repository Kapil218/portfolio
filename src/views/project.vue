<template>
  <v-row class="mt-6">
    <v-col
      v-for="(pro, index) in projects"
      :key="index"
      cols="12"
      class="text-xs-center"
    >
      <v-card class="my-3 light-blue lighten-4 ma-4">
        <template v-if="index % 2 === 0">
          <!-- Image on the right -->
          <v-row>
            <v-col cols="6">
              <v-card-title
                class="black--text mt-8 ml-3"
                style="font-size: 1.5rem; font-family: cursive"
              >
                {{ pro.title }}
              </v-card-title>
              <v-card-subtitle class="text--caption"
                >Developer Name - kapil</v-card-subtitle
              >
              <v-card-text
                class="black--text text--lighten-5"
                style="height: 100px"
              >
                <div>{{ pro.content }}</div>
              </v-card-text>
              <v-card-actions>
                <v-btn
                  :href="pro.link"
                  color="black"
                  style="width: 60%"
                  class="pink white--text mx-auto"
                  text
                >
                  Source code
                </v-btn>
              </v-card-actions>
            </v-col>
            <v-col cols="6">
              <v-img :src="pro.i" height="200px"></v-img>
            </v-col>
          </v-row>
        </template>
        <template v-else>
          <!-- Image on the left -->
          <v-row>
            <v-col cols="6">
              <v-img :src="pro.i" height="200px"></v-img>
            </v-col>
            <v-col cols="6">
              <v-card-title
                class="black--text mt-8 ml-3"
                style="font-size: 1.5rem; font-family: cursive"
              >
                {{ pro.title }}
              </v-card-title>
              <v-card-subtitle class="text--caption"
                >Developer Name - kapil</v-card-subtitle
              >
              <v-card-text
                class="black--text text--lighten-5"
                style="height: 100px"
              >
                <div>{{ pro.content }}</div>
              </v-card-text>
              <v-card-actions>
                <v-btn
                  :href="pro.link"
                  color="black"
                  style="width: 60%"
                  class="pink white--text mx-auto"
                  text
                >
                  Source code
                </v-btn>
              </v-card-actions>
            </v-col>
          </v-row>
        </template>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
export default {
  data() {
    return {
      projects: [
        {
          title: "Host4u",
          i: require("/src/assets/3.jpg"),
          content:
            "it is an online cloud storage platform which provides hosting services at very lmarginal cost ",
          link: "https://github.com/Kapil218/Host4U",
        },
        {
          title: "Vibe",
          i: require("/src/assets/1.jpg"),
          content:
            "An music player with basic commands like -play ,pause etc  and gives you an musical vibe.",
          link: "https://github.com/Kapil218/Music",
        },
        {
          title: "Mait-Hostel",
          i: require("/src/assets/2.jpg"),
          content:
            " Mait hostel web with all of the  info of services, food etc  .",
          link: "https://github.com/Kapil218/Hostel",
        },
      ],
    };
  },
};
</script>

<style scoped></style>
