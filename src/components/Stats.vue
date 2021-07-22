<template>
  <div class="Stats bg-cover bg-no-repeat bg-bottom bg-center relative sm:py-8  xl:pt-32 lg:pt-32 mb-48 mt-8"
       :style="`background-image:url(${grande3horizontal}); border-radius:50px; min-height:300px; background-position:
        center bottom: -6rem` ">
    <div class="w-full h-full bg-customCream opacity-50 absolute top-0 left-0 z-0 rounded-3xl"></div>
    <div class="Stats-Components container flex flex-col lg:flex-row items-center justify-between w-full z-50 relative lg:absolute px-8">
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
