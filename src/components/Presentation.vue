<template>
<!--  El mayor cambio aca es que pasamos de md:flex-row a lg: para qeu se vea mucho mejor-->
  <div class="Presentation lg:flex flex-col lg:flex-row " :class="{ 'lg:flex-row-reverse': content.left}">
<!--    la clase que le estoy bindeando se lee: cuando el content este del lado izquierdo aplicar la clase
FLEX ROW REVERSE que esuna funcionalidad de flex -->
    <div v-for="col, colIndex in content.columns" :key="colIndex" class="flex-1 ">
      <div v-if="col.imgSrc">
        <img :src="col.imgSrc" alt="image" >
      </div>
        <div v-else class="p-24" :class="`bg-${col.backgroundColor} text-${ content.left ? 'black' : 'white'}`">
          <div class="mb-8">
          <h2 class="text-4xl font-bold uppercase mb-20">{{ col.title }}</h2>
<!--          subrayado de visita argentina  es el h-1 w-16 -->
            <div class="h-1 w-16">
          </div>
        </div>

        <p class="font-bold uppercase mb-4">{{ col.subtitle }}</p>
        <p class="font-light">{{ col.description }}</p>
      </div>

    </div>
  </div>
</template>

<script>
  export default {
    props: {
      content:{
        default: () => {},
        type: Object
      }
    },
    setup(props){
      console.log(props.content)
    }
  }
</script>

