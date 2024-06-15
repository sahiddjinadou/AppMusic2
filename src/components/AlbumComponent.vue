<template>
  <section class="article-section">
      <article v-for="(album, index) in albums" :key="index" class="article-container">
        <h2>{{ album.genre }}</h2>
        <div>
          <RouterLink to="#">{{ album.title }}</RouterLink>
          <p class="text">
            {{ album.description }}
          </p>
        </div>
        <div>
          <ul>
            <li v-for="(track, index) in album.tracks" :key="index" >{{ track.title }}</li>
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
.article-container {
  /* margin-inline:1rem;
  padding-block: 2rem; */
    background: white;
    /* box-shadow: 0 1px 1px rgba(0, 0, 0, 0.2),
	            0 8px 0 -3px #f6f6f6,
	            0 9px 1px -3px rgba(0, 0, 0, 0.2),
	            0 16px 0 -6px #f6f6f6,
	            0 17px 2px -6px rgba(0, 0, 0, 0.2); */
    /* border: 1px solid rgb(25, 0, 255); */
    margin-block:2rem;
    padding-inline: .3rem;
    padding-block: .5rem;
   

}
.article-container > h2 {
  background-color:var(--secondColor)
}


ul {
  
}

li {
  list-style: none;
  margin: .3rem;
}
.text {
    border: 1px solid;
}

</style>