<template>
  <div class="Tabs">
    <header class="flex flex-row justify-center items-center mb-4 cursor-pointer">
      <div v-for="obj, objIndex in tabs" :key="objIndex"  class="Tabs-Header-Item px-6 py-4 mx-3" :class="objIndex === activeTab ? 'text-customCream border-b-4 border-customCream' : 'border-b'"  >
        {{ obj.title }}
      </div>
    </header>
    <div>

    </div>
  </div>

</template>

<script>
import {reactive, toRefs} from 'vue';
import landscape1 from '../assets/landscape1.jpg';

export default {
  setup() {
    const data = reactive ({
      activeTab: 0,
      tabs: [{
        imgSrc: landscape1,
        title: 'Design',
        description: 'La va a tocar para Diego, ahí la tiene Maradona, lo marcan dos, pisa la pelota Maradona,' +
            ' arranca por la derecha el genio del fútbol mundial,' +
            ' deja el tendal y va a tocar para Burruchaga... ¡Siempre Maradona! ¡Genio! ¡Genio!'
      },
        {
          imgSrc: landscape1,
          title: 'Performance',
          description: 'La va a tocar para Diego, ahí la tiene Maradona, lo marcan dos, pisa la pelota Maradona,' +
              ' arranca por la derecha el genio del fútbol mundial,' +
              ' deja el tendal y va a tocar para Burruchaga... ¡Siempre Maradona! ¡Genio! ¡Genio!'
        },
        {
          imgSrc: landscape1,
          title: 'Goals',
          description: 'La va a tocar para Diego, ahí la tiene Maradona, lo marcan dos, pisa la pelota Maradona,' +
              ' arranca por la derecha el genio del fútbol mundial,' +
              ' deja el tendal y va a tocar para Burruchaga... ¡Siempre Maradona! ¡Genio! ¡Genio!'
        }]
    })
    return {
      ...toRefs(data)
    }
  }
}
</script>

<style scoped>

</style>