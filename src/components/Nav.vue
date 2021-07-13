<template>
  <div class="Nav container mx-auto my-8 grid grid-flow-col grid-cols-2 gap-4">
    <div>
      <img :src="Logo" alt="Argentina Logo" class="w-16 mx-auto md:mx-0">
    </div>
   <div class="hidden md:block">
     <div class="grid grid-flow-col grid-cols-3 gap-4 items-center h-full">
       <p v-for="option, optionIndex in menu" :key="optionIndex" @click="openLink(option.link)"
          class="cursor-pointer text-xs font-bold">{{ option.title}}</p>
     </div>
   </div>
    <div class="block md:hidden fixed right-8 top-8 cursor-pointer">
      <img :src="MenuIcon" alt="Display Menu" class="w-8">
    </div>
  </div>
</template>

<script setup>
//importo el logo de argentina
import Logo from '../assets/logo1.png'
import MenuIcon from '../assets/iconomenu.png'

const menu = [{
  title: 'Foto 1',
  link: '',
},
  {
    title: 'Foto 2',
    link: '',
  },
  {
    title: 'Foto 3',
    link: '',
  },
];

const openLink =(link) =>  {
window.open(link)
}
</script>
asdas