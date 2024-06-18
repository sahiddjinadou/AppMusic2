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
    <div class="grille">
      <!-- Details -->
      <ContenuAlbumComponent  v-if="showDetails" :album="oneAlbum"/>
      <!-- contenues -->
      <div>
        <section>
          <form class="form" >
            <input type="search" name="" id="">
            <input type="submit"  class="button-83" value="Rechercher">
          </form>
          <h1>Page principale Album Music</h1>
        </section>
        <AlbumComponent :albums="albums" @upState = 'upShowDetails' @albumData = 'upAlbum'/>
      </div>
    </div>
    
  </main>
</template>



<style scoped>
.form {
  display:  flex;
  justify-content: center;
  gap: 20px;
  margin-block: 2rem;
}
.main-container section:first-of-type {
  text-align: center;
  margin-block:1rem;
}
.grille {
  display:grid;
}
[type="search"]{
  padding: 1rem;
  font-size: 20px;
}


/* CSS */
.button-83 {
  appearance: button;
  background-color: transparent;
  background-image: linear-gradient(to bottom, #fff, #f8eedb);
  border: 0 solid #e5e7eb;
  border-radius: .5rem;
  box-sizing: border-box;
  color: #482307;
  column-gap: 1rem;
  cursor: pointer;
  /* display: flex; */
  font-family: ui-sans-serif,system-ui,-apple-system,system-ui,"Segoe UI",Roboto,"Helvetica Neue",Arial,"Noto Sans",sans-serif,"Apple Color Emoji","Segoe UI Emoji","Segoe UI Symbol","Noto Color Emoji";
  font-size: 100%;
  font-weight: 700;
  line-height: 24px;
  margin: 0;
  outline: 2px solid transparent;
  padding: 1rem 1.5rem;
  text-align: center;
  text-transform: none;
  transition: all .1s cubic-bezier(.4, 0, .2, 1);
  user-select: none;
  -webkit-user-select: none;
  touch-action: manipulation;
  box-shadow: -6px 8px 10px rgba(81,41,10,0.1),0px 2px 2px rgba(81,41,10,0.2);
}

.button-83:active {
  background-color: #f3f4f6;
  box-shadow: -1px 2px 5px rgba(81,41,10,0.15),0px 1px 1px rgba(81,41,10,0.15);
  transform: translateY(0.125rem);
}

.button-83:focus {
  box-shadow: rgba(72, 35, 7, .46) 0 0 0 4px, -6px 8px 10px rgba(81,41,10,0.1), 0px 2px 2px rgba(81,41,10,0.2);
}
@media (min-width: 600px) {
  .grille{
    display: flex;
    justify-content: space-between;
    gap: 100px;
  }
  /* .grille{
    grid-template-columns: 20% 75%;
    gap: 50px;
  } */
}
</style>
