<template>
  <div class="grid grid-flow-col">
    <div
      class="m-2 p-2 rounded border border-black flex justify-between bg-white bg-opacity-50"
    >
      <div class="text-align">
        <h3 class="text-lg font-bold">{{ classesName }}</h3>
        <p class="font-bold">{{ classes.name }}</p>
        <p>Dés de vie: {{ classes.Vie }}</p>
        <p>Caractéristique Principale: {{ classes.Carac }}</p>
        <p>Caractéristique d'incantation: {{ classes.incant }}</p>
        <p>Maitrise jet de Sauvegarde : {{ classes.save }}</p>
    
      </div>
      <base-button text="Voir plus" @click="showModal = true"> </base-button>
    </div>
    <div class="modal-overlay h-full" v-if="showModal" @click="showModal = false"></div>
    <div class="modal" v-if="showModal">
      <h3 class="text-lg font-bold">{{ classesName }}</h3>
        <p class="font-bold">{{ classes.name }}</p>
        <p><b>Dés de vie:</b> {{ classes.Vie }}</p>
        <p><b>Caractéristique Principale:</b> {{ classes.Carac }}</p>
        <p><b>Caractéristique d'incantation: </b>{{ classes.incant }}</p>
        <p><b>Maitrise jet de Sauvegarde : </b>{{ classes.save }}</p>
      <br />

      <img :src="classeImage(classes.image)" alt="" />
      <br />
      
    </div>
  </div>
</template>

<script>
export default {
  name: "classes-card",
  props: ["classes"],
 data() {
    return {
      showModal: false,
    };
  },
  methods: {
    classeImage(img) {
      return require("@/assets/img/classes/" + img);
    },
  },
};
</script>
<style  scoped>
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