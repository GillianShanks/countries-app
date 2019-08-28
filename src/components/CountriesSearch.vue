<template lang="html">
  <div class="">
    <h3>Search for a country:</h3>
    <input type="text" v-model="typedCountry" @change="sendCountry"/>

  </div>
</template>

<script>
import {eventBus} from "../main.js"

export default {
  name: "country-search",
  props: ['countries'],
  data(){
    return {
      typedCountry: ""
    }
  },
  methods:{
    sendCountry: function(){
      for (let country of this.countries){
        if (this.typedCountry === country.name){
          return eventBus.$emit('country-selected', country)
        };
      }
    }
  }
}
</script>

<style lang="css" scoped>
</style>
