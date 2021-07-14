<template>
  <div>
      <Nav></Nav>
    <MainHeader> </MainHeader>
    <p>{{ hello }}</p>
    <Presentation  v-for="obj, objIndex in presentations" :key="objIndex" :content="obj"></Presentation>


<!--    <Stats></Stats>-->
<!--    <Tabs></Tabs>-->
<!--    <Footer></Footer>-->

  </div>
</template>

<script >
import { MainHeader, Nav, Presentation, Stats, Tabs, Footer } from '../components';
import { reactive, toRefs } from 'vue' ;
import fotopequeña1 from '../assets/pequeña1.jpg';

export default {
  components: {
    MainHeader,
    Nav,
    Presentation
  },
  setup() {
    let data = reactive({
      presentations: [{
          left: true,
        columns: [{
          title: 'Visita Argentina',
          subtitle: 'Un pais con buena gente',
          description: 'La Argentina tiene muchas particularidades que han recorrido el mundo en boca de sus visitantes.' +
              ' La personalidad desenvuelta de su gente, amigable, divertida y efusiva; la gastronomía típica que va desde' +
              ' el asado hasta el mate, pasando por los platos regionales y bocaditos con dulce de leche; las danzas tradicionales' +
              ' como el tango, baile de parejas a un ritmo de 2 por 4 que nace en Buenos Aires en el siglo XIX y hoy es difundido' +
              ' internacionalmente,' +' ó el folklore, con las diferentes formas coreográficas que adopta en cada región;' +
              'Imposible olvidar, la pasión por el fútbol'
        },
          {
            imgSrc: fotopequeña1
          },
        ],
        }]
      })

    return{
      ...toRefs(data)
    }
  }
}
</script>