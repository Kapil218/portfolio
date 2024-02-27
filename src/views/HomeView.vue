<template>
  <div class="home">
    <h1>Home</h1>
    <p>{{ apiData }}</p>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "HomeView",
  data() {
    return {
      apiData: [],
    };
  },
  async mounted() {
    this.apiData = await axios
      .get("https://api.coindesk.com/v1/bpi/currentprice.json")
      .then((response) => (this.info = response));
  },
};
</script>
