<template>
  <!--  El mayor cambio aca es que pasamos de md:flex-row a lg: para qeu se vea mucho mejor-->
  <div class="Presentation lg:flex flex-col lg:flex-row bg-customCream m-4 opacity-" :class="{ 'lg:flex-row-reverse': content.left}"
       style="border-radius: 50px">

    <!--La clase que le estoy bindeando se lee: cuando el content este del lado izquierdo aplicar la clase
    FLEX ROW REVERSE que esuna funcionalidad de flex -->

    <div v-for="col, colIndex in content.columns" :key="colIndex" class="flex-1 m-4" style="border-radius: 50px">

      <div v-if="col.imgSrc">
        <img :src="col.imgSrc" alt="image" style="border-radius: 50px">
      </div>

<!-- // VISIT ARGENTINA TEXTO // -->

      <div v-else class="p-20">
<!--         al lado del p-20 va esto :class="`bg-${col.backgroundColor} text-${ content.left ? 'black' : 'white'}`"-->
        <div class="mb-16">
          <h2 class="text-4xl font-bold uppercase mb-2">{{ col.title }}</h2>
          <!--          subrayado de visita argentina  es el h-1 w-16 -->
          <div class="h-1 w-1"> ______</div>
        </div>
        <p class="font-bold uppercase mb-8">{{ col.subtitle }}</p>
        <p class="font-light">{{ col.description }}</p>
      </div>

    </div>


  </div>
</template>

<script>
import GeneralMixin from "../mixins/GeneralMixin";

export default {
  mixins: [GeneralMixin],
  setup(props){
    console.log(props.content)
  }
}
</script>

