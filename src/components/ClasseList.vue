<template>
  <div >
    
    <h1 class="text-3xl font-bold text-center">
       {{ classesData.name }}
    </h1>
 
    <classes-card
      v-for="(classes, index) in classesData.classes"
      :key="index"
      :classes="classes"
      
    >
    </classes-card>
    
  </div>
</template>

<script>
import classesData from "../assets/data/classes.json";
import ClassesCard from "./ClassesCard";


export default {
  name: "classes-list",
  components: {
    ClassesCard,
   
  },
  data() {
    return {
      classesData: classesData,
      
    };
  },
  
};
</script>

<style></style>
