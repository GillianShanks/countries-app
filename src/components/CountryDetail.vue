<template lang="html">
  <div class="" v-if="country">
    <h3>{{country.name}}</h3>
    <p>{{country.region}}</p>
    <p>{{country.capital}}</p>
    <p>{{country.popular}}</p>
  </div>
</template>

<script>
export default {
  name: "country-detail",
  props: ['country']
}
</script>

<style lang="css" scoped>
</style>
