<template>
  <aside class="aside1">
    <div>
      <div class="metadata">
        <h2 class="title">{{ album?.title }}</h2>
        <p> <strong>{{ album?.artist }}</strong></p>
        <button @click="sendProgress" class="btn-play">
          <p> play</p>
          <p class="poster"> <img src="../assets/img/play_btn.png" alt="play"></p>          
        </button>
      </div>
      <img :src="album?.coverImage" alt="image">
    </div>
  
    <div class="list">
      <h3> List of songs </h3>
      <ul>
        <li v-for="track in album?.tracks" :key="track.trackNumber" class="flex song">
          <p>{{ track.title }}</p>
          <p>{{ track.duration }}</p>
        </li>
      </ul>
    </div>
  </aside>
</template>

<script setup>
import { ref, watch } from "vue";

const props = defineProps({
  album: Object,
});



const canShowprogressBar = ref(true)

const emit = defineEmits(["progress"]);

const sendProgress = () => {
  emit("progress", canShowprogressBar.value)
  
}

</script>

<style scoped>

.poster {
  width: 30px;
  height: 30px;
}
[alt="image"] {
  width: 100%;
  height: 100%;
}
.list h3 {
  background-color: #3333ee;
  padding: 1rem;
  color: white;
  font-family: "Ubuntu";
  font-size: 20px;
}
.song p:first-child {
  font-family: "Playwrite România";
  font-weight: bold;
}
.aside1 {
  padding-block: 1rem;
  display: flex;
  flex-direction: column;
  gap: 20px;
  border-radius:10px ;
  height: 60%;
  width: 750px;
  box-shadow: 5px 5px 10px;
}
.song:hover{
  background-color: beige;
  
}
.song {
  padding: .5rem 1rem;
}
.aside1 >:first-child {
  display: flex;
  flex-direction: column-reverse;
  justify-content: center;
  align-items: center;
}
.metadata {
  display: flex;
  flex-direction: column;
  gap: 10px;
  
}
.flex {
  display: flex;
  justify-content: space-between;
}

.btn-play{
background-color: rgba(70, 122, 233, 0.856);
border: none;
display: flex;
justify-content: center;
align-items: center;
gap: 10px;
padding-inline: 1rem;
padding-block: .4rem;
border-radius: 10px;

}
.btn-play:hover{
  background-color: rgba(0, 0, 255, 0.884);
}

.btn-play> :first-child{
  font-family: "Ubuntu";
  color:white;
  font-size: 15px;
  text-transform: capitalize;
}
[alt= "play"] {
  border: 1px solid;
  width:30px;
  height:30px;
  border-radius: 50%;
  border: 2px solid white;
}

strong{
  font-family: "Playwrite România";
  font-size: 21px;
  font-weight: bold;
}

.title{
  font-family: "Ubuntu";
  margin-block: 1rem;
}
</style>