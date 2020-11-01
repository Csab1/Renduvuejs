<template>
  <div class="grid grid-flow-col">
    <div
      class="m-2 p-2 rounded border border-black flex justify-between bg-white bg-opacity-50"
    >
    
      <div class="text-align">
        <h3 class="text-lg font-bold">{{ raceName }}</h3>
        <p class="font-bold">{{ races.name }}</p>
        <p>Caractéristique : {{ races.carac }}</p>
        <p>Taille : {{ races.taille }}</p>
        <p>Vitesse : {{ races.vitesse }}</p>
        <p>Competence : {{ races.Competence }}</p>
        <p>Langue : {{ races.langue }}</p>
      </div>
      <base-button text="Voir plus" @click="showModal = true"> </base-button> 
      
    </div>
   
      <div class="modal-overlay h-full" v-if="showModal" @click="showModal = false"></div>
    <div class="modal" v-if="showModal">
     
     
      <p class="text-3xl font-bold">{{ races.name }}</p>
      <p> <b>Caracteristique</b>  : {{ races.carac }}</p>
      <p><b>Taille</b> : {{ races.taille }}</p>
      <p><b>Vitesse</b> : {{ races.vitesse }}</p>
      <p> <b>Competences</b> : {{ races.details.comp1}} <br> {{races.details.comp2}} <br> {{races.details.comp3}} <br> {{races.details.comp4}} <br> {{races.details.comp5}} <br> {{races.details.comp6}} </p>
      <p><b>Langue</b> : {{ races.langue }}</p>
      <img class="   pl-42 " :src="raceImage(races.image)" alt="" />

  

      
      
      <br />
     
    </div>
  </div>
 
</template>

<script>
export default {
  name: "race-card",
  props: ["races"],
  data() {
    return {
      showModal: false,
    };
  },
  methods: {
    raceImage(img) {
      return require("@/assets/img/race/" + img);
    },
   
  },
};
</script>

<style scoped>
.modal {
  position:fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  z-index: 99;
  
  max-width:60;
  max-height: 100%;
  background-color: #fff;
  border-radius: 16px;
  padding: 25px;
  align-self: center;
}

.modal-overlay {
 position: fixed;
 top: 0;
 left: 0;
 right: 0;
 bottom: 0;
 height: 100%;
 background-color: rgba(0, 0, 0, 0.5);
}
</style>