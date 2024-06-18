<template>
    <div class="navLogo-container">
        <div class="navLogo">
            <div class="logo">
                <strong>Zik'Art</strong>
            </div>

            <nav>
                <RouterLink to="/">Home</RouterLink>
                <RouterLink to="/login">Se connecter</RouterLink>
          </nav>
        </div>
        
        <div>
            <Chronometre />
        </div>

    </div>
</template>

<script setup lang='ts'>
import { RouterLink, RouterView } from 'vue-router';
import Chronometre from "./Chronometre.vue";

</script>


<style scoped>

.navLogo-container {
    width: 100%;
    height: 6vh;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding-inline: 1rem;
    padding-block: 2rem;
    background-color: var(--fistColor);
    color: white;
}
.navLogo {
    display: flex;
    justify-content: space-between;
    align-items: center;
}
.logo {
    margin-inline: .5rem;
    font-size: 1.5rem;
}




/* Responsive */
@media (min-width: 1024px) {
    .navLogo {
    display: flex;
    justify-content: space-around;
    align-items: center;
}

.logo {
    margin-inline: 1.5rem;
    font-size: 2.5rem;
}

nav {}

}
</style>

