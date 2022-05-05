<template>
    <main>
        <TrackList/>
    </main>
</template>

<style lang="scss" scoped>
    main{
        background-color: $sp-main;
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
