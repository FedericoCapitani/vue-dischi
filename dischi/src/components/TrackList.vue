<template>
    <div>
        <section class="tracks" v-if="!loading">
            <div class="container">
                <div>
                <Track :track="track" v-for="(track, index) in tracks" :key="index"/></div>
            </div>
        </section>
            <div v-else class="loading">
                <h1>loading ...</h1>
            </div>
  </div>
</template>

<script>
import axios from "axios";
import Track from "@/components/TrackComponent";
export default {
  name: "TrackListComponent",
  components: {
    Track,
  },
  data() {
    return {
      API_URL: "https://flynn.boolean.careers/exercises/api/array/music",
      tracks: null,
      loading: true,
      error: null,
    };
  },
  methods: {
    callApi() {
      axios
        .get(this.API_URL)
        .then((response) => {
          this.tracks = response.data;
          this.loading = false;
        })
        .catch((error) => {
          console.error();
          error;
          this.error = `Sorry There is a problem! ${error}`;
        });
    },
  },
  mounted() {
    this.callApi();
  },
};
</script>