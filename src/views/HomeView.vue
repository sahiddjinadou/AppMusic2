<script setup>
import { ref, onMounted } from 'vue';
import data from '@/assets/data';

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

    <section class="article-section">
      <article v-for="(album, index) in albums" :key="index" class="article-container">
        <h2>{{ album.genre }}</h2>
        <div>
          <RouterLink to="#">{{ album.title }}</RouterLink>
          <p>
            {{ album.description }}
          </p>
        </div>
        <div>
          <ul>
            <li>item1</li>
            <li>item2</li>
            <li>item3</li>
            <li>item4</li>
            <li>item5</li>
            <li>item6</li>
            <li>item7</li>
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
  </main>
</template>



<style scoped>
.main-container section:first-of-type {
  text-align: center;
  margin-block:1rem;
}
.article-container {
  /* margin-inline:1rem;
  padding-block: 2rem; */
    background: white;
    box-shadow: 0 1px 1px rgba(0, 0, 0, 0.2),
	            0 8px 0 -3px #f6f6f6,
	            0 9px 1px -3px rgba(0, 0, 0, 0.2),
	            0 16px 0 -6px #f6f6f6,
	            0 17px 2px -6px rgba(0, 0, 0, 0.2);
    border: 1px solid rgb(25, 0, 255);
    margin-block:2rem;
    padding-inline: .3rem;
    padding-block: .5rem;

}
.article-container > h2 {
  background-color:var(--secondColor)
}
.article-container article {
}
ul {
  display: flex;
}

li {
  list-style: none;
  margin: .5rem;
}


</style>
