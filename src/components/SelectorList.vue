<template>

<div>
<form class="w-full max-w-sm">
    <label >Entrer un nom</label>
    <input >
    <p>Selectionner une race</p>
  <select v-model="selected">
      <option disabled value="">Choisisser une Race</option>
      <option  v-for="(races, index) in racesData.races"
      :key="index"
      :races="races"
     >{{races.name}} </option>
  </select>
  <p>Selectionner une classe</p>
   <select v-model="selected">
      <option disabled value="">Choisisser une Classe </option>
      <option   v-for="(classes, index) in classesData.classes"
      :key="index"
      :classes="classes"
     >{{classes.name}} </option>
  </select>
  </form>
  </div>
</template>

<script>
import racesData from "../assets/data/races.json";
import classesData from '../assets/data/classes.json'
export default {
name:"selector-list",

 data() {
    return {
      racesData: racesData,
      classesData : classesData,
      
    };
  },




}
</script>

<style>

</style>