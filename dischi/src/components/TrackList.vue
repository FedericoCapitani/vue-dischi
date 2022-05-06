<template>
    <div>
        <section class="tracks" v-if="!loading">
            <div class="container">
            <!-- <div class="card" v-for="(track, index) in tracks" :key="index">
                <img :src="track.poster" alt="" />
                <h2 class="info">{{ track.title}}</h2>
                <div class="info">{{ track.author }}</div>
                <div class="info">{{ track.year }}</div>
            </div> -->
            <Track :track="track" v-for="track in tracks" :key="track.title"/>
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
      axios.get(this.API_URL).then((response) => {
        console.log(response);
          this.tracks = response.data.response;
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