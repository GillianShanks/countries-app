<template lang="html">
  <div class="" v-if="country">
    <h3>{{country.name}}</h3>
    <p>Region: {{country.region}}</p>
    <p>Capital: {{country.capital}}</p>
    <p>Population: {{country.population}} people</p>
    <img :src="country.flag" alt="country flag">
    <p>Language(s):</p>
    <ul>
      <li v-for="(language,index) in country.languages" :key="index">{{language.name}}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "country-detail",
  props: ['country']
}
</script>

<style lang="css" scoped>
img{
  width: 15em;
}
</style>
