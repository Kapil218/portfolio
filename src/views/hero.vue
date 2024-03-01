<template>
  <v-row
    justify="center"
    align="center"
    :style="{ padding: isMobile ? '4rem 12px' : '4rem' }"
  >
    <v-col
      v-if="isMobile"
      cols="12"
      sm="6"
      md="4"
      class="profile-img white--text text-center pb-8"
    >
      <!-- <img :src="src" alt="Avatar" /> -->
      <v-avatar size="200">
        <v-img
          :src="src"
          @mouseover="changeImage"
          @mouseout="resetImage"
          alt="Avatar"
          class="avatar-img"
        />
      </v-avatar>
    </v-col>
    <v-col
      cols="12"
      md="8"
      sm="6"
      class="intro white--text pb-8"
      align-self="center"
      ><p style="font: 500 normal 2.5em 'tahoma'; color: rgb(22, 223, 234)">
        Hola!
      </p>
      <p style="font: 500 normal 2.5em 'tahoma'; color: rgb(209, 42, 209)">
        I'm Kapil Singh Rathore
      </p>
      <p class="word">{{ currentWord }} |</p>
      <p class="text-h6 primary--text my-4">
        Always eager to learn new technologies and develop new things based on
        it.
      </p>
      <p
        class="grey--text mt-4 mb-12"
        style="word-spacing: 5px; font-size: large"
      >
        I thrive on tackling complex challenges and finding innovative solutions
        to meet project goals. Whether it's creating intuitive user interfaces
        or optimizing website performance, I'm committed to delivering results
        that exceed expectations.
      </p>
      <div :class="isMobile ? 'text-center' : ''">
        <span class="rounded-pill pa-5" style="border: 1px solid grey">
          <v-btn
            v-for="(icon, i) in icons"
            :key="i"
            class="mx-4 my-3 white--text icon"
            icon
            :href="icon.link"
            target="_blank"
          >
            <v-icon size="40px">
              {{ icon.icon }}
            </v-icon>
          </v-btn>
        </span>
      </div>
    </v-col>
    <v-col
      cols="12"
      v-if="!isMobile"
      sm="6"
      md="4"
      class="profile-img white--text text-center pb-8"
    >
      <!-- <img :src="src" alt="Avatar" /> -->
      <v-avatar size="300">
        <v-img
          :src="src"
          @mouseover="changeImage"
          @mouseout="resetImage"
          alt="Avatar"
          class="avatar-img"
        />
      </v-avatar>
    </v-col>
  </v-row>
</template>
<script>
export default {
  name: "Hero",

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
      words: ["Software Engineer ", "Developer Expert for Web"],
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
  computed: {
    isMobile() {
      return this.$vuetify.breakpoint.xsOnly;
    },
  },
  mounted() {
    this.len = this.words.length;
    setInterval(this.wordflick, this.speed);
  },

  methods: {
    handleScroll() {
      const parentElement = this.$el;
      const children = parentElement.querySelectorAll(".loading");
      const windowHeight = window.innerHeight;

      children.forEach((child, index) => {
        const rect = child.getBoundingClientRect();
        const isVisible = rect.top >= 0 && rect.bottom <= windowHeight;
        if (isVisible) {
          this.activeChildIndex = index;
        }
      });
    },
    changeImage() {
      this.src = require("@/assets/profile222.jpeg");
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
  transform: scale(1.2);
}
.word {
  margin: auto;
  color: rgb(92, 181, 94);
  font: 500 normal 2.5em "tahoma";
  text-shadow: 5px 2px #222324, 2px 4px #222324, 3px 5px #222324;
}

.avatar-img:hover {
  animation: load 2s;
}
@keyframes load {
  0% {
    opacity: 0.4;
  }

  100% {
    opacity: 1;
    scale: 1.2;
  }
}
.intro {
  animation: loading-intro 2s ease-out 1s;
}
@keyframes loading-intro {
  0% {
    opacity: 0.2;
    transform: translateX(-1000%);
  }
  100% {
    opacity: 1;
    transform: translateX(0%);
  }
}
.profile-img {
  animation: loading-image 2s ease-out 1s;
}
@keyframes loading-image {
  0% {
    opacity: 0.2;
    transform: translateX(1000%);
  }
  100% {
    opacity: 1;
    transform: translateX(0%);
  }
}
</style>
