<template>
  <div id="app">
    <Header/>
    <Main/>
  </div>
</template>

<script>
import Header from "@/components/SiteHeader.vue"
import Main from "@/components/SiteMain"

export default {
  name: 'App',
  components: {
    Header,
    Main
  }
}
</script>

<style lang="scss">
@import '~@/assets/scss/style.scss';
</style>
