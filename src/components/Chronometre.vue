<template>
    <div>
         <span v-if="heure < 10">0</span> {{heure}} h : <span v-if="minute < 10">0</span> {{minute}} min : <span v-if="seconde < 10">0</span> {{ seconde }} s
    </div>
</template>

<script setup>
import { ref, watch } from "vue";
const seconde = ref(0);
const minute = ref(0);
const heure = ref(0);

function chrono(){
    seconde.value++;

    if(seconde.value == 60)  {
        minute.value++;
        seconde.value = 0
    } else if(minute.value == 60) {
        heure.value++;
        minute.value = 0;
        seconde.value = 0;
    }


}
const setInter = setInterval(chrono, 1000);

</script>

<style scoped>

</style>