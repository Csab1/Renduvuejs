<template>
<body>
  <div>
    <nav-bar
    @change-component="updateSelectedComponent">
    </nav-bar>
  
<keep-alive>
    <component :is="selectedComponent"
    v-bind="currentProps"></component>
    </keep-alive>
    
  </div>
  </body>
</template>

<script>
import RaceList from "./components/RaceList"
import NavBar from "./components/navigation/NavBar"
import ClassesList from "./components/ClasseList"
import SelectorList from "./components/SelectorList"



export default {
  name: "App",

  components: {
    RaceList,
    NavBar,
    ClassesList,
    SelectorList
   
    
  
    
  },
  data() {
    return {
      selectedComponent: 'race-list',
    }
  },
  computed:{
    currentProps(){
if(this.selectedComponent=="classes-list"){
  return {selection: this.selectedComponent}
}
if(this.selectedComponent=="selector-list"){
  return {selection: this.selectedComponent}
}
return false
    }
  },
  methods: {
    updateSelectedComponent(comp) {

      this.selectedComponent = comp
    }
  }
}
</script>

<style>

body{
background-image: url(./assets/img/background.jpg);
background-size: cover;


}
</style>
