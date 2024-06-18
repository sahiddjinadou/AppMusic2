<template>
  <section class="section">
    <article v-for="(album, index) in albums" :key="index" class="article-container">
      <h2 class="title">{{ album.genre }}</h2>
      <div class="flex-col">
        <RouterLink to="#" class="router-class">{{ album.title }}</RouterLink>
        <p class="text">
          {{ album.description }}
        </p>
      </div>
      <div>
        <ul class="flex-row">
          <li v-for="( tag, index) in album.tags" :key="index" class="ul-items">{{ tag }}</li>
        </ul>
      </div>
  
      <div>
        <ul class="flex-row ">
          <li class="details border">
            <span> en </span>
          </li>
          <li class="flex-row details ">
           <img class="image" src="../assets/img/favorite.png" alt="favorite">
           <span> 5 </span>
          </li>
          <li class="flex-row details  ">
           <img class="image" src="../assets/img/timerPlay.png" alt="favorite">           
           <span> {{ album.duration }} min</span>
          </li>
          <li  >
            <button class="details border btn" @click="showDetails(album)"> Details </button>
          </li>
        </ul>
      </div>
    </article>
  
  </section>
</template>

<script setup>
import albums from '@/assets/data';
import { ref } from 'vue';

const props = defineProps({
  albums: Array
})

const emit = defineEmits(["albumData","upState"])
const detailsState = ref(false)

const showDetails = (element)=>{
  emit("albumData",element) ; 
  detailsState.value = true ; 
  emit("upState",detailsState.value)
}


</script>

<style scoped>
.btn {
  font-family: "Playwrite România";
  background-color: #fff;
  display: block;
  width: 100%;
  height: 100%;
}
.btn:hover{
  background-color: rgb(177, 177, 177);
  transition: .5s;
}
.details {
  padding-block:.3rem;
  padding-inline: .5rem;
}
.border{
  border:1px solid rgb(204, 196, 196);
  border-radius:5px
}
.image{
  display: block;
  width: 25px;
  height: 25px;
}
.title {
  border-radius: 10px 10px 0px 0px;
  background-color: aquamarine;
  padding: .5rem;
  font-family: "Ubuntu";
}

.flex-col {
  display: flex;
  flex-direction: column;
  gap: .5rem;
}

.section {
  padding: 1rem;
}

.article-container {
  display: flex;
  flex-direction: column;
  gap: 10px;
  border: 1px dotted green;
  border-radius: 10px;
  margin-block: 15px;
}


.flex-row {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
}

.ul-items {
  padding-block: .5rem;
  padding-inline: .8rem;
  background-color: rgb(12, 126, 88);
  color: white;
  font-family: "Ubuntu";
}

li {
  list-style: none;
  margin: .3rem;
}

.text {
  padding: .3rem;

}

.router-class {
  color: black;

  padding: .5rem;
  font-size: 18px;
  font-weight: bold;
  background-color: white;
}

.router-class:hover {
  text-decoration: underline;
}
</style>