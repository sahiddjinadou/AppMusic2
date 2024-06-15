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
            <li v-for="( tag, index) in album.tags" :key="index" class="ul-items" >{{ tag }}</li>
          </ul>
        </div>
  
        <div>
          <ul>
            <li>en</li>
            <li>5</li>
            <li>840min</li>
            <li>Details</li>
          </ul>
        </div>
      </article>

    </section>
</template>

<script setup>
import albums from '@/assets/data';

const props = defineProps({
    albums : Array
})
</script>

<style scoped>
.title{
  background-color: aquamarine;
  padding:.5rem ;
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
  border: 1px solid red;
  margin-block:15px ;
}


.flex-row {
  display: flex;
  flex-direction: row;
}

.ul-items {
  padding-block: .5rem;
  padding-inline: 1rem;
  background-color:rgb(12, 126, 88);
  color: white;
  font-family: "Ubuntu";
}
li {
  list-style: none;
  margin: .3rem;
}
.text {
  padding: .5rem;
    
}
.router-class {
  color: black;
  
  padding: .5rem;
  font-size: 18px;
  font-weight: bold;
  background-color: white;
}
.router-class:hover{
  text-decoration: underline;
}

</style>