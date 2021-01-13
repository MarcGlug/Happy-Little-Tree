<template>
    <div class="buttons">
      <button @click="save">Enregistrer</button>
      <button @click="clear">Effacer</button>
    </div>
</template>

<script>

export default {

  name: 'Choucroute',
  methods: {
    save () {
      const canvas = document.querySelector('canvas')
      const picture = canvas.toDataURL()
      const tmpLink = document.createElement('a')
      tmpLink.download = 'myDrawing.png'
      tmpLink.href = picture
      document.body.appendChild(tmpLink)
      tmpLink.click()
      document.body.removeChild(tmpLink)
    },
    clear () {
      const canvas = document.querySelector('canvas')
      const ctx = canvas.getContext('2d')
      ctx.clearRect(0, 0, canvas.width, canvas.height)
      ctx.beginPath()
      ctx.fillStyle = 'white'
      ctx.fillRect(0, 0, canvas.width, canvas.height)
    }
  }
}
</script>

<style lang="scss" scoped>

 .buttons{
   display: flex;
   justify-content: space-around;
   margin:25px
 }

 button{
   font-family: Avenir, Helvetica, Arial, sans-serif;
   font-size: 15px;
   font-weight: 600;
   color: white;
   -webkit-font-smoothing: antialiased;
   -moz-osx-font-smoothing: grayscale;
   text-align: center;
   padding: 15px;
   width: 120px;
   border-radius: 50px;
   border-width: 0px;
   background-color: #0078d7;
   transition: box-shadow 0.2s;
   &:hover{
     box-shadow:3px 5px 7px 2px rgb(168, 168, 168);
   }
 }

</style>
