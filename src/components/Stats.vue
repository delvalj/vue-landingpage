<template>
  <div class="Stats bg-cover bg-bottom bg-center bg-no-repeat "
       :style="`background-image:url(${grande3horizontal}); height:450px;`">
    <div class="w-full h-full bg-customCream opacity-50 relative"></div>
    <div class="Stats-Components z-50 relative font-bold">
        <p class="text-white">some text </p>
    </div>
  </div>
</template>


<script setup>
import StatsCard from './elements/stats/StatsCard.vue';
import grande3horizontal from '../assets/grande2.jpg';
</script>

aaa