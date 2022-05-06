<template>
    <div class="navbar">
        <img src="@/assets/img/logo.png" alt="">
        <SearchBox v-model="searchText" @formSubmit="search"/>
    </div>
</template>

<style lang="scss" scoped>
    .navbar{
        background-color: $sp-card;
        padding: 1rem 2rem;
        img{
            width: 80px;
        }
    }
</style>

<script>
import SearchBox from "@/components/SearchBox.vue";
import state from '@/state.js';
export default {
  name: 'SiteHeader',
  components: {
    SearchBox
  },
  data(){
    return {
      searchText: ''
    }
  },
  methods: {
    search(){
      console.log('Searching...');
      console.log(this.searchText);
      state.searchText = this.searchText;
      console.log(state);
    }
  }
};
</script>