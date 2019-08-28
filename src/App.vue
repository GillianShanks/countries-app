<template lang="html">
  <div class="">
    <a href="https://www.youtube.com/watch?v=dQw4w9WgXcQ">Click me, Kyle</a>
    <h1>Country Navigator</h1>
    <countries-list :countries="countries"></countries-list>
  </div>
  
</template>

<script>
import CountriesList from './components/CountriesList.vue';

export default {
  name: "app",
  data(){
    return {
      countries:[],
      selectedCountry: null
    }
  },
  mounted(){
    fetch('https://restcountries.eu/rest/v2/all')
    .then(response => response.json())
    .then(countries => this.countries=countries)
  }
}
</script>

<style lang="css" scoped>
</style>
