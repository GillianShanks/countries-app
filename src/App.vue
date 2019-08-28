<template lang="html">
  <div class="">
    <a href="https://www.youtube.com/watch?v=dQw4w9WgXcQ">Click me, Kyle</a>
    <h1>Country Navigator</h1>
    <div class="container">
      <countries-dropdown :countries="countries"></countries-dropdown>

      <countries-list :countries="countries"></countries-list>
      <country-detail  :country="selectedCountry"></country-detail>
    </div>

  </div>

</template>

<script>
import CountriesList from './components/CountriesList.vue';
import CountryDetail from './components/CountryDetail.vue';
import CountriesDropdown from './components/CountriesDropdown.vue';
import {eventBus} from './main.js';

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

    eventBus.$on('country-selected', (country) => {
      this.selectedCountry = country;
    })
  },
  components: {
    "countries-list": CountriesList,
    "country-detail": CountryDetail,
    "countries-dropdown": CountriesDropdown
  }
}
</script>

<style lang="css" scoped>
.container {
  display: flex;
  justify-content: space-between;
}

</style>
