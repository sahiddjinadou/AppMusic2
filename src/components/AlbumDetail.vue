<template>
  <div v-if="!album">
    <p>
      Désolé, le titre
      <span class="title-not-found"
        >'{{ albumTitle.split("-").join(" ") }}'</span
      >
      n'a aucune correspondance dans nos données
    </p>
  </div>

  <div v-else class="container">
    <h4 class="genre">{{ album.genre }}</h4>
    <h2  class="title">{{ album.title }}</h2>
    <p class="description">{{ album.description }}</p>
    <p class="duration">
      Duration : <span>{{ album.duration }}</span>
    </p>
    <p class="like">like :</p>

    <div class="tags">
      <span v-for="(tag, index) in album.tags" :key="index">{{ tag }}</span>
    </div>

    <div class="div-img">
      <img :src="album.coverImage" :alt="`image du titre ${album.title}`" />
    </div>
  </div>
</template>

<script setup >
import { useRoute } from "vue-router";
import { recupAlbum } from "@/assets/data.js";

const route = useRoute();
const title = route.params.albumTitle;
const props = defineProps(["albumTitle"]);

const album = recupAlbum(title);
</script>

<style scoped>
.container {
  margin-top: 10px;
  width: 80%;
  padding-bottom: 20px;
  margin:  40px auto 0;
  background-color: white;
  padding-inline: 15px;
}
.div-img {
  width: 90%;
  margin: 0 auto;
}

img {
  width: 100%;
  height: 500px;
  object-fit: cover;
}

.genre {
    /* margin-inline: 25px; */
    background-color: var(--fistColor);
    padding: 10px;
    color: #adff2f;
    font-weight: bold;
    font-family: "Ubuntu", serif;
}

.tags {
    display: flex;
    justify-content: space-around;
    flex-wrap: wrap;
    gap: 10px;
    margin-bottom: 20px;
}

.like {
    margin-bottom: 15px;
}

.duration,
.like,
.title,
.description {
    font-family:'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif
}

/* Partie Tags */
.tags span {
  align-items: center;
  appearance: none;
  background-color: #fff;
  border-radius: 24px;
  border-style: none;
  box-shadow: rgba(0, 0, 0, .2) 0 3px 5px -1px,rgba(0, 0, 0, .14) 0 6px 10px 0,rgba(0, 0, 0, .12) 0 1px 18px 0;
  box-sizing: border-box;
  color: #3c4043;
  cursor: pointer;
  display: inline-flex;
  fill: currentcolor;
  font-family: "Google Sans",Roboto,Arial,sans-serif;
  font-size: 14px;
  font-weight: 500;
  height: 48px;
  justify-content: center;
  letter-spacing: .25px;
  line-height: normal;
  max-width: 100%;
  overflow: visible;
  padding: 2px 24px;
  position: relative;
  text-align: center;
  text-transform: none;
  transition: box-shadow 280ms cubic-bezier(.4, 0, .2, 1),opacity 15ms linear 30ms,transform 270ms cubic-bezier(0, 0, .2, 1) 0ms;
  user-select: none;
  -webkit-user-select: none;
  touch-action: manipulation;
  width: auto;
  will-change: transform,opacity;
  z-index: 0;
}

.tags span:hover {
  background: #F6F9FE;
  color: #174ea6;
}

.tags span:active {
  box-shadow: 0 4px 4px 0 rgb(60 64 67 / 30%), 0 8px 12px 6px rgb(60 64 67 / 15%);
  outline: none;
}

.tags span:focus {
  outline: none;
  border: 2px solid #4285f4;
}

.tags span:not(:disabled) {
  box-shadow: rgba(60, 64, 67, .3) 0 1px 3px 0, rgba(60, 64, 67, .15) 0 4px 8px 3px;
}

.tags span:not(:disabled):hover {
  box-shadow: rgba(60, 64, 67, .3) 0 2px 3px 0, rgba(60, 64, 67, .15) 0 6px 10px 4px;
}

.tags span:not(:disabled):focus {
  box-shadow: rgba(60, 64, 67, .3) 0 1px 3px 0, rgba(60, 64, 67, .15) 0 4px 8px 3px;
}

.tags span:not(:disabled):active {
  box-shadow: rgba(60, 64, 67, .3) 0 4px 4px 0, rgba(60, 64, 67, .15) 0 8px 12px 6px;
}

.tags span:disabled {
  box-shadow: rgba(60, 64, 67, .3) 0 1px 3px 0, rgba(60, 64, 67, .15) 0 4px 8px 3px;
}

/************************************************* */
</style>

