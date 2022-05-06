<template>
  <div class="card bg_card">
    <img :src="track.poster" alt="" />
    <h2 class="info_title">{{ track.title}}</h2>
    <div class="info">{{ track.author }}</div>
    <div class="info">{{ track.year }}</div>
  </div>
</template>

<script>
export default {
    name: 'TrackComponent',
    props : {
        track: Object
    }
};
</script>

<style lang="scss" scoped>
    .info_title{
        text-align: center;
        color: white;
        font-size: 1.5rem;
    }
    .info{
        text-align: center;
        color: grey;
    }
    .bg_card{
        background-color: $sp-card;
    }
</style>