<template>
  <div id="app">
    <h1>Happy little tree</h1>
    <Canvas></Canvas>
    <Pannel :colors="colors"></Pannel>
  </div>
</template>

<script>
import Canvas from './components/Canvas.vue'
import Pannel from './components/Pannel.vue'

export default {
  name: 'App',
  data () {
    return {
      colors: [
        '#2D2D2D',
        '#d84841', // rouge
        '#ab5e29', // brun
        '#E8B732', // jaune
        '#35AD39', // vert
        '#27AA7A', // turquoise
        '#3DABCC', // bleu
        '#3237AB', // bleu profond
        '#5F3098', // violet
        '#C7398B', // rose
        '#B7B7B7', // gris
        '#db635d', // mid rouge
        '#b47b54', // mid brun
        '#EAC46C', // mid jaune
        '#69C76C', // mid vert
        '#5FB899', // mid turquoise
        '#79C3DD', // mid bleu
        '#6064B8', // mid bleu profond
        '#7E5DAC', // mid violet
        '#D871A8', // mid rose
        'white',
        '#ec8984', // light rouge
        '#dbab8b', // light brun
        '#F7E3B6', // light jaune
        '#BAEDBC', // light vert
        '#BEE1D5', // light turquoise
        '#C1E5F1', // light bleu
        '#9D9FDA', // light bleu profond
        '#BCA8D4', // light violet
        '#E7AAC8' // light rose
      ]
    }
  },
  components: {
    Canvas,
    Pannel
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
