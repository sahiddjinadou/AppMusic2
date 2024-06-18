<template>
    <div v-if="!album">
        <p>Désolé, le titre <span class="title-not-found">'{{ albumTitle.split("-").join(" ") }}'</span> n'a aucune correspondance dans nos données</p>
    </div>

    <div v-else>
        <h4>{{  album.genre }}</h4>
        <h2>{{ album.title }}</h2>
        <p>{{  album.description }}</p>
        <p>Duration : <span>{{ album.duration }}</span></p>
        <p>like : </p>

        <div class="tags">
            <span v-for="(tag, index) in album.tags" :key="index">{{ tag }}</span>
        </div>

        <div class="img">
            <img :src="album.coverImage" :alt="`image du titre ${album.title}`">
        </div>
    </div>
</template>

<script setup >
import {useRoute} from "vue-router";
import { recupAlbum } from "@/assets/data.js";

const route = useRoute();
const title = route.params.albumTitle;
const props = defineProps(["albumTitle"]);

const album = recupAlbum(title);
</script>

<style scoped>

</style>