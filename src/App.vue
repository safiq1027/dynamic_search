<script setup>
import{ ref} from 'vue'
import { countries } from './data/countries';
const search=ref('')

function getFilteredCountries() {
  return countries.filter(country => {
    return country.name.toLowerCase().startsWith(search.value.toLowerCase())
  })
}
</script>
<template>
  <section>
    <h1 class="text-2xl">Vue Form </h1>
    <p class="ml-10 mt-5">{{ search }}</p>
    <div class="mt-10 p-5">
      <label class="p-5" for="">search :</label>
    <input class="border border-gray-400 w-52 p-5" type="text" v-model="search">
    </div>
    <p >
      <ul>
        <li class="ml-32 mt-2 mb-2" v-for="country in getFilteredCountries()"> {{country.name}}</li>
      </ul>
    </p>
    
  </section>

</template>
<style scoped>
</style>