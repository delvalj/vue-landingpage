<template>
  <div>
      <Nav></Nav>
    <MainHeader> </MainHeader>
    <Presentation  v-for="obj, objIndex in presentations" :key="objIndex" :content="obj"></Presentation>
    <Stats></Stats>
    <Tabs></Tabs>
<!--    <Footer></Footer>-->

  </div>
</template>

<script >
import { MainHeader, Nav, Presentation, Stats, Tabs, Footer } from '../components';
import { reactive, toRefs } from 'vue' ;
import medio2 from '../assets/2.jpg';
import medio1 from '../assets/grande3horizontal.jpg';

export default {
  components: {
    MainHeader,
    Nav,
    Presentation,
    Stats,
    Tabs
  },
  setup() {
    let data = reactive({
      presentations: [{
          left: false,
        columns: [{
            backgroundColor: "customCream",
          title: 'Visita Argentina',
          subtitle: 'Un pais con buena gente',
          description: 'La Argentina tiene muchas particularidades que han recorrido el mundo en boca de sus visitantes.' +
              ' La personalidad desenvuelta de su gente, amigable, divertida y efusiva; la gastronomía típica que va desde' +
              ' el asado hasta el mate, pasando por los platos regionales y bocaditos con dulce de leche; las danzas tradicionales' +
              ' como el tango, baile de parejas a un ritmo de 2 por 4 que nace en Buenos Aires en el siglo XIX y hoy es difundido' +
              ' internacionalmente'
        },{
            imgSrc: medio2
          }]
        }, {
          left: true,
          columns: [{
            backgroundColor: "white",
            button: {
              backgroundColor: "customCream",
              text: 'Elige tu Destino'
            },

            title: 'Visita Argentina',
            subtitle: 'Un pais con buena gente',
            description: 'La Argentina tiene muchas particularidades que han recorrido el mundo en boca de sus visitantes.' +
                ' La personalidad desenvuelta de su gente, amigable, divertida y efusiva; la gastronomía típica que va desde' +
                ' el asado hasta el mate, pasando por los platos regionales y bocaditos con dulce de leche; las danzas tradicionales' +
                ' como el tango, baile de parejas a un ritmo de 2 por 4 que nace en Buenos Aires en el siglo XIX y hoy es difundido' +
                ' internacionalmente,' +' ó el folklore, con las diferentes formas coreográficas que adopota en cada región;' +
                'Imposible olvidar, la pasión por el fútbol'
          },{
            imgSrc: medio1
          }]
        },
      ]
      })

    return{
      ...toRefs(data)
    }
  }
}
</script>