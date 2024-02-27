<template>
  <v-container fluid class="black gg" style="height: 100%; padding-top: 4rem">
    <v-row style="margin-bottom: 8rem">
      <v-col cols="12" md="8" class="white--text pl-12" align-self="center"
        ><p style="font: 500 normal 2.5em 'tahoma'; color: rgb(22, 223, 234)">
          Hola!
        </p>
        <p class="word">{{ currentWord }} |</p>
        <p class="text-h6 my-4">
          A passionate web developer dedicated to crafting engaging and
          user-friendly digital experiences.
        </p>
        <p class="grey--text mt-4" style="word-spacing: 5px">
          I thrive on tackling complex challenges and finding innovative
          solutions to meet project goals. Whether it's creating intuitive user
          interfaces or optimizing website performance, I'm committed to
          delivering results that exceed expectations.
        </p>
        <p class="grey--text mt-4" style="word-spacing: 5px">
          I prefer to keep learning, continue challenging myself, and do
          interesting things that matter. Fueled by high energy levels and
          boundless enthusiasm, I’m easily inspired and more then willing to
          follow my fascinations wherever they take me.
        </p>
      </v-col>
      <v-col cols="12" md="4" class="white--text text-end">
        <v-spacer></v-spacer>
        <!-- <img :src="src" alt="Avatar" /> -->
        <img
          :src="src"
          @mouseover="changeImage"
          @mouseout="resetImage"
          alt="Avatar"
          class="avatar-img"
        />
      </v-col>
    </v-row>
    <hr />
    <technologiesVue />
    <hr />
    <experienceVue />
    <hr />
    <resumeVue />
    <connectVue />
  </v-container>
</template>

<script>
import connectVue from "./connect.vue";
import experienceVue from "./experience.vue";
import technologiesVue from "./technologies.vue";
import resumeVue from "./resume.vue";
export default {
  name: "Home",
  components: { connectVue, technologiesVue, experienceVue, resumeVue },
  data() {
    return {
      src: require("@/assets/profile.png"),
      words: ["Welcome to my portfolio!", "I'm Kapil Singh Rathore"],
      currentWord: "",
      part: "",
      i: 0,
      offset: 0,
      len: 0,
      forwards: true,
      skip_count: 0,
      skip_delay: 15,
      speed: 70,
    };
  },

  mounted() {
    this.len = this.words.length;
    setInterval(this.wordflick, this.speed);
  },

  methods: {
    changeImage() {
      this.src = require("@/assets/profile22.jpeg");
    },
    resetImage() {
      this.src = require("@/assets/profile.png");
    },

    wordflick() {
      if (this.forwards) {
        if (this.offset >= this.words[this.i].length) {
          ++this.skip_count;
          if (this.skip_count === this.skip_delay) {
            this.forwards = false;
            this.skip_count = 0;
          }
        }
      } else {
        if (this.offset === 0) {
          this.forwards = true;
          this.i++;
          this.offset = 0;
          if (this.i >= this.len) {
            this.i = 0;
          }
        }
      }
      this.part = this.words[this.i].substr(0, this.offset);
      if (this.skip_count === 0) {
        if (this.forwards) {
          this.offset++;
        } else {
          this.offset--;
        }
      }
      this.currentWord = this.part;
    },
  },
};
</script>

<style scoped>
.word {
  margin: auto;
  color: rgb(92, 181, 94);
  font: 500 normal 2.5em "tahoma";
  text-shadow: 5px 2px #222324, 2px 4px #222324, 3px 5px #222324;
}

.avatar-img {
  transition: transform 1s ease;
  max-width: 90%;
  object-fit: contain; /* Ensures the image maintains aspect ratio */
  border-radius: 12rem 0rem 0rem 12rem;
}

.avatar-img:hover {
  transform: scale(1.01);
  border-radius: 12rem 0rem 0rem 12rem;
}

.gg {
  /* Fallback color */
  background-color: #000000;

  /* Gradient */
  background-image: linear-gradient(to bottom right, #0f1010, #0e0d0e);
}
</style>
