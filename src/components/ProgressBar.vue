<template>
    <div v-if="showBar">
        <div class="progress-container" >
            <div class="ProgressBar" :style="`width:${increment}%`"> </div>
            <div class="base"><strong class="strong">Artiste :</strong> {{ album?.artist }} . <strong class="strong">Titre: </strong>{{album.title}}</div>
        </div>
        <div class="strong">{{ currentMorceau}}/{{ nbrMorceaux }} </div>
    </div>
</template>

<script setup>
const props = defineProps({
  album: Object,
  stateVisible: Boolean
})
import { ref, watch } from "vue";
const currentMorceau = ref(1)
const nbrMorceaux = ref(0)
const dureeAlbum = ref(0)
const increment = ref(0)
const tab = ref([])
const curseur = ref(0)
const id = ref()
const showBar = ref(false)
const times = ref(0)
function reinitialisation() {
  curseur.value = 0
  tab.value = []
}

async function inProgress() {
  //je recupere la duree du premier morceaux
  increment.value += ((parseInt(tab.value[curseur.value]) * 100) / dureeAlbum.value)
  id.value = setTimeout(() => {
    times.value = parseInt(tab.value[curseur.value]) * 1000
    curseur.value++
    currentMorceau.value++
    console.log(curseur.value);
    if (curseur.value >= tab.value.length - 1) {
      increment.value += ((parseInt(tab.value[curseur.value]) * 100) / dureeAlbum.value)
      console.log("fin");
      clearTimeout(id)
      reinitialisation()
    } else {
      console.log(times.value);
      console.log("tete " + increment.value);
      inProgress()

    }
  }, times.value);

}

watch(() => props.album, (newValue, oldValue) => {
  showBar.value = props.stateVisible
  reinitialisation()
  //recuperation de la duree de chaque music dans un tableau
  newValue.tracks.forEach(element => {
    tab.value.push(element.duration.split(':')[0])
  });
  // le nombre de morceaux
  nbrMorceaux.value = tab.value.length
  // le temps maximum mi pour lire tout l'album
  dureeAlbum.value = tab.value.reduce((acc, el) => acc + parseInt(el), 0)
  times.value = parseInt(tab.value[curseur.value]) * 1000

  console.log(times.value);
  clearTimeout(id.value)
  increment.value = 0;
  currentMorceau.value = 1
  inProgress()
})


</script>

<style scoped>
.strong{
    font-weight: 800;
    font-size: 15px;
}
.progress-container {
    position: relative;
    border-radius: 20px;

}

.base {
    color: black;
    font-family: "Ubuntu";
    border-radius: 20px;
    border: 1px solid wheat;
    height: 30px;
}

.ProgressBar {
    height: 30px;
    border-radius: 20px;
    position: absolute;
    background-color: rgba(94, 20, 214, 0.336);


}
</style>