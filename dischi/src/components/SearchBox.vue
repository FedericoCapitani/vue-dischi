<template>
  <form class="d-flex" @submit.prevent="$emit('formSubmit')">
    <input 
    class="form-control me-2" 
    type="search" 
    placeholder="Search" 
    aria-label="Search" 
    :value="searchText"
    v-on:input="$emit('input', $event.target.value)"
    @keyup="$emit('formSubmit')"
    />
    <button class="btn d-flex align-items-center btn_search" type="submit">
      Search
    </button>
  </form>
</template>

<script>
export default {
  name: 'SearchBox',
  props: {
    searchText: String 
  }
}
</script> 