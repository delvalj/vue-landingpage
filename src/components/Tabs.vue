<template>
  <div class="Tabs">
    <header class="flex flex-row  items-center justify-center mb-4">
      <div  v-for="obj, objIndex in tabs" :key="objIndex"  class="Tabs-Header-Item px-6 py-4 mx-3 cursor-pointer"
           :class="objIndex === activeTab ? 'text-customCream border-b-4 border-customCream' : 'border-b'" @click="updateActiveTab(objIndex)">
        {{ obj.title }}
      </div>
    </header>
    <div class="container mx-auto bg-cover bg-no-repeat flex items-center justify-center mb-4" :style="`border-radius: 50px; background-image:url(${getActiveTabContent.imgSrc});min-height:450px;
     background-position: ;`">
        <div class="mb-16">
          <h2 class="text-4xl text-center uppercase font-bold f mb-4"> {{ getActiveTabContent.title }}</h2>
          <p class="text-xl px-28 py-8"> {{getActiveTabContent.description}}</p>
          <div class="h-1 w-16"></div>
        </div>
    </div>
  </div>
</template>

<script>
import {reactive, toRefs, computed} from 'vue'
import landscape1 from '../assets/jujuy.jpg'

export default {
  setup() {
    const data = reactive ({
      activeTab: 0,
      getActiveTabContent: computed(() => {
        return data.tabs[data.activeTab]
      }),
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

    const updateActiveTab = (objIndex) => {
      data.activeTab = objIndex
    }

    return {
      updateActiveTab,
      ...toRefs(data)
    }
  }
}
</script>

<style scoped>

</style>