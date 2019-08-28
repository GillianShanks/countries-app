<template lang="html">
  <div class="">
    <select v-model="dropdownCountry" @change="handleChange">
      <option default value="">Select Country</option>
      <option v-for="(country, index) in countries" :value="country" :key="index">{{country.name}}</option>
    </select>
  </div>
</template>

<script>
import {eventBus} from '../main.js';

export default {
  name: 'countries-dropdown',
  props: ['countries'],
  data(){
    return {
      dropdownCountry: null
    }
  },
  methods: {
    handleChange() {
      eventBus.$emit('country-selected', this.dropdownCountry)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
