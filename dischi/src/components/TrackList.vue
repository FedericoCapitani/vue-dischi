<template>
    <div>
        <section class="tracks" v-if="!loading">
            <div class="container">
            <Track :track="track" v-for="track in filteredTracks" :key="track.title"/>
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
import state from '@/state.js';
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
  computed: {
    filteredTracks() {
        return this.tracks.filter(track => {
          return track.title.toLowerCase().includes(state.searchText.toLowerCase())
        })
     
    }
  },
  mounted() {
    this.callApi();
  },
};
</script>