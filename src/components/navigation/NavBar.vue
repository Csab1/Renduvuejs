<template>
    <div class="bg-white p-2 ">
      <img class="h-12 inline-block" src="../../assets/img/logo.png" > 
      <a class="text-red-600 text-2xl "
      v-for="(link, index) in navigation"
      :key="index"
       href="#" 
       @click="selectComponent(link.component)"
       >
       |
       {{link.name}}
        </a>
      
    </div>
</template>

<script>

export default {
name: "nav-bar",
data(){
return{

  navigation: [
{name:"Les Races",component:"race-list"},
{name:"Les Classes",component:"classes-list"},
{name:"Creation",component:"selector-list"}


  ]
 
}


},
 methods: {
    selectComponent(comp) {
     this.$emit('change-component', comp)
    },
  }
}
</script>

<style>

</style>