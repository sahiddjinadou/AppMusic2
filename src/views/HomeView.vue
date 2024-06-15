<template>
  <main>
    <section>
      <form action="#">
        <input type="search" name="" id="">
        <input type="submit" value="Rechercher">
      </form>
      <h1>Page principale Album Music</h1>
    </section>
    <section>

    </section>
    <article>
      <h2>Jazz</h2>
      <div>
        <RouterLink to="#">Lumière Céleste</RouterLink>
        <p>
          Plongez dans une expérience spirituelle transcendante avec "Lumière Céleste", le dernier opus du talentueux artiste gospel, Donald Kossi. Cet album est bien plus qu'une simple collection de chansons, c'est un voyage émotionnel profondément connecté à la foi et à la transcendance.
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
  </main>
</template>


<script setup>
import data from '@/assets/data'

console.log(data);

</script>


<style scoped>
ul {
  display: flex;
}

li {
  list-style: none;
  margin: .5rem;
}


</style>
