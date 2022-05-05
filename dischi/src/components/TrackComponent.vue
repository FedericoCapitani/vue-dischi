<template>
  <div class="card" >
    <img :src="track.poster" alt="" />
    <h2 class="info">{{ track.title}}</h2>
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
    h2{
        color: white;
    }
    .info{
        text-align: center;
    }
    .info > div{
        color: gray;
    }
</style>