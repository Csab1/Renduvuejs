<template>
  <div>
    
    <h1 class="text-3xl font-bold text-center">
       {{ racesData.name }}
    </h1>
    
    <race-card
    
      v-for="(races, index) in racesData.races"
      :key="index"
      :races="races"
     
     
    >
    </race-card>
  </div>
</template>

<script>
import racesData from "../assets/data/races.json";
import RaceCard from "./RaceCard";


export default {
  name: "race-list",
  components: {
    RaceCard,
   
  },
  data() {
    return {
      racesData: racesData,
      
    };
  },
 
}
</script>

<style>
</style>
