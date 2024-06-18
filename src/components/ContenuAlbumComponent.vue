<template>
  <aside>
    <div>
      <div>
        <h2 class="title">{{ album?.title }}</h2>
        <p> <strong>{{ album?.artist }}</strong></p>
        <button @click="sendProgress" class="btn-play">
          <p> play</p>
          <p> <img src="../assets/img/play_btn.png" alt="play"></p>          
        </button>
      </div>
      <img :src="album?.coverImage" alt="image">
    </div>
  
    <div class="list">
      <h3> List of song </h3>
      <ul>
        <li v-for="track in album?.tracks" :key="track.trackNumber" class="flex">
          <p>{{ track.title }}</p>
          <p>{{ track.duration }}</p>
        </li>
      </ul>
    </div>
  </aside>
</template>

<script setup>
import { ref } from "vue";

const props = defineProps({
  album: Object
});

const canShowprogressBar = ref(false)

const emit = defineEmits(["progress"]);

const sendProgress = () => {
  emit("progress", canShowprogressBar)
}

</script>

<style scoped>
.flex {
  display: flex;
  justify-content: space-between;
}

.btn-play{
background-color: red;
border: none;
display: flex;
}
.btn-play >:first-child,
.btn-play >:last-child
{
  border:1px solid

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