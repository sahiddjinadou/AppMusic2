<script setup>
import { RouterLink, RouterView } from 'vue-router'
import Navigation from '@/components/NavComponent.vue'
</script>

<template>
  <header>
    <Navigation></Navigation>
  </header>

  <main>
    <RouterView />
  </main>

</template>

<style scoped>



</style>
