<template>
  <aside>
    <div>
      <h2>{{ album.title }}</h2>
      <p> Name : {{ album.artist }}</p>
      <img :src="album.coverImage" alt="image">
    </div>

    <div class="list">
      <h3> List of song </h3>
      <ul>
        <li v-for="track in album.tracks" :key="track.trackNumber" class="flex">
          <p>{{ track.title }}</p>
          <p>{{ track.duration }}</p>
        </li>
      </ul>
    </div>


  </aside>
</template>

<script setup>
const props = defineProps({
    album:Object
})
</script>

<style>
.flex {
  display: flex;
  justify-content: space-between;
}
</style>