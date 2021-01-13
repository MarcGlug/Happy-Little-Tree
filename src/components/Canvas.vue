<template>
    <canvas :width="width" :height="height"><p>hello</p></canvas>
</template>

<script>

export default {
  name: 'Canvas',
  props: {
    width: {
      type: String,
      default: '500px'
    },
    height: {
      type: String,
      default: '500px'
    }
  }
}

// DRAW SECTION
window.onload = function () {
  var color = '#2D2D2D' // couleur par defaut
  var strength = document.querySelector('input#pixel').value
  // --------------------------------------------------------------------------------

  const canvas = document.querySelector('canvas')
  const ctx = canvas.getContext('2d')
  const offsetX = canvas.offsetLeft
  const offsetY = canvas.offsetTop
  let canDraw = false
  ctx.beginPath()
  ctx.fillStyle = 'white'
  ctx.fillRect(0, 0, canvas.width, canvas.height)
  function draw (e) {
    if (canDraw) {
      ctx.lineCap = 'round'
      ctx.lineWidth = strength
      ctx.strokeStyle = color
      ctx.lineTo(e.x - offsetX, e.y - offsetY)
      ctx.stroke()
      ctx.beginPath()
      ctx.moveTo(e.x - offsetX, e.y - offsetY)
    }
  }

  canvas.addEventListener('mousedown', (e) => {
    canDraw = true
    const selectedColorButton = document.querySelector('li.selected')
    strength = document.querySelector('input#pixel').value
    if (selectedColorButton !== null) {
      color = selectedColorButton.style.backgroundColor
    }
    draw(e) // permet de dessiner sans bouger pour prendre en compte le cas des points
  })

  canvas.addEventListener('mouseup', () => {
    canDraw = false
    ctx.beginPath()
  })

  canvas.addEventListener('mousemove', draw)
}

</script>

<style lang="scss" scoped>

canvas {
   border: 2px solid #d3d3d3;
}

</style>
