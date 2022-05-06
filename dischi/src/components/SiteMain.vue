<template>
    <main>
        <TrackList/>
    </main>
</template>

<style lang="scss" scoped>
    main{
        background-color: $sp-main;
        min-height: calc(100vh - 112px);
        padding: 2rem 0;
    }
</style>

<script>
import TrackList from "@/components/TrackList"

export default {
    name: "SiteMain",
    components: {
        TrackList
    }
}
</script>
