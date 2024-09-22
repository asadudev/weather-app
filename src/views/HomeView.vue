<template>
  <main class="container text-white">
    <div class="pt-4 mb-8 relative">
      <input 
        type="text"
        v-model="searchQuery"
        placeholder="Search for a city state"
        class="py-2 px-1 w-full bg-transparent border-b focus:border-weather-secondary focus:outline-none focus:shadow-[0px_1px_0_0_#004E71]" 
      />
    </div>
  </main>
</template>
<script setup>
import axios from 'axios';
import { ref } from 'vue';

const searchQuery = ref("");
const queryTimeout = ref(null);
const 

const getSearchResult = () =>{
  queryTimeout.value = setTimeout(()=>{
    if(searchQuery.value !== ""){
      const result = await axios.get(`https://api.mapbox.com/geocoding/v5/mapbox.places/${searchQuery.value}.json`)
    }
  })
}
</script>
