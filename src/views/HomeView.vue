<template>
  <v-container fluid class="black gg" style="height: 100%; padding-top: 4rem">
    <v-row style="margin-bottom: 8rem" justify="end">
      <v-col cols="12" md="8" class="white--text pl-12" align-self="center"
        ><p style="font: 500 normal 2.5em 'tahoma'; color: rgb(22, 223, 234)">
          Hola!
        </p>
        <p class="word">{{ currentWord }} |</p>
        <p class="text-h6 primary--text my-4">
          Always eager to learn new technologies and develop new things based on
          it.
        </p>
        <p class="grey--text mt-4" style="word-spacing: 5px; font-size: large">
          I thrive on tackling complex challenges and finding innovative
          solutions to meet project goals. Whether it's creating intuitive user
          interfaces or optimizing website performance, I'm committed to
          delivering results that exceed expectations.
        </p>
        <v-btn
          v-for="(icon, i) in icons"
          :key="i"
          class="mr-8 my-4 white--text icon"
          icon
          :href="icon.link"
          target="_blank"
        >
          <v-icon size="40px">
            {{ icon.icon }}
          </v-icon>
        </v-btn>
      </v-col>
      <v-col cols="8" sm="6" md="4" class="white--text text-end">
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
    <hr />
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
      src: require("@/assets/profile.png"),
      words: [
        "I'm Kapil Singh Rathore",
        "Software Engineer ",
        "Developer Expert for Web",
      ],
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
.icon {
  transition: transform 0.4s ease;
}
.icon:hover {
  transform: scale(1.3);
}
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
