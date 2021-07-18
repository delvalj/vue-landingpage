<template>
  <div class="Stats bg-cover bg-no-repeat bg-bottom bg-center relative pt-24 mb-48"
       :style="`background-image:url(${grande3horizontal}); height:300px; background-position:
        center bottom: -6rem` ">
    <div class="w-full h-full bg-customCream opacity-50 absolute top-0 left-0 z-0"></div>
    <div class="Stats-Components container mx-auto flex items-center justify-between w-full z-50 relative">
      <Stats-Card v-for="obj, objIndex in cards" :key="objIndex" :content="obj" ></Stats-Card>
    </div>
  </div>
</template>


<script>
import {reactive, toRefs} from 'vue'
import cuadrado1 from '../assets/acumulador.png';
import cuadrado2 from '../assets/bombilla.png';
import cuadrado3 from '../assets/peligro.png';
import cuadrado4 from '../assets/linterna.png';

import StatsCard from './elements/stats/StatsCard.vue';
import grande3horizontal from '../assets/grande2.jpg';


export default {
  components: {
    StatsCard
  },
  //agrego informacion que va a ser loopeada por el v-for arriba.. los cuadrados del medio
  setup() {
    const data = reactive ({
      grande3horizontal,
      cards: [{
        imgSrc: cuadrado1,
        title: "acumulador",
        description: "Precio : 250 , <br> Calidad: Alta"
      }, {
        imgSrc: cuadrado2,
        title: "bombilla",
        description: "algo algo lago "
      }, {
        imgSrc: cuadrado3,
        title: "peligro",
        description: "algo algo lago "
      }, {
        imgSrc: cuadrado4,
        title: "linterna",
        description: "algo algo lago"
      }]
    })
    return {
      ...toRefs(data)
    }
  }
}
</script>
