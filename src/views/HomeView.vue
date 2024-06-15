<script setup>
import { ref, onMounted } from 'vue';
import data from '@/assets/data';
import AlbumComponent from '@/components/AlbumComponent.vue';

//Notre tableau contenant les albums
const albums = data;

console.log(data);

</script>

<template>
  <main class="main-container">
    <section>
      <form action="#">
        <input type="search" name="" id="">
        <input type="submit" value="Rechercher">
      </form>
      <h1>Page principale Album Music</h1>
    </section>

    <AlbumComponent :albums="albums"/>
    
  </main>
</template>



<style scoped>
.main-container section:first-of-type {
  text-align: center;
  margin-block:1rem;
}


</style>
