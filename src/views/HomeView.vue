<script setup>
import { ref, onMounted } from 'vue';
import data from '@/assets/data';
import AlbumComponent from '@/components/AlbumComponent.vue';
import ContenuAlbumComponent  from "@/components/ContenuAlbumComponent.vue";

//Notre tableau contenant les albums
const albums = data;

const showDetails = ref(false)

const upShowDetails = (event)=>{
  showDetails.value = event
}

const oneAlbum = ref()
const upAlbum = (event)=>{
  oneAlbum.value = event
}
</script>

<template>
  <main class="main-container">
    <div class="gille">
      <!-- Details -->
      <ContenuAlbumComponent  v-if="showDetails" :album="oneAlbum"/>
      <!-- contenues -->
      <div>
        <section>
          <form action="#">
            <input type="search" name="" id="">
            <input type="submit" value="Rechercher">
          </form>
          <h1>Page principale Album Music</h1>
        </section>
        <AlbumComponent :albums="albums" @upState = 'upShowDetails' @albumData = 'upAlbum'/>
      </div>
    </div>
    
  </main>
</template>



<style scoped>
.main-container section:first-of-type {
  text-align: center;
  margin-block:1rem;
}
.grille {
  display:grid;
  grid-auto-columns: 1fr;
}

</style>
