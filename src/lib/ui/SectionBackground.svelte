<script lang="ts">
  import { onMount } from "svelte"

  type Star = {
    x: number
    y: number
    radius: number
    vx: number
    vy: number
  }

  let myCanvas: HTMLCanvasElement | null = null
  let ctx: CanvasRenderingContext2D | null = null

  const stars: Star[] = [] // Array that contains the stars
  const FPS = 60 // Frames per second
  const x = 100 // Number of stars
  const mouse = {
    x: 0,
    y: 0,
  } // mouse location

  onMount(() => {
    if (!myCanvas) return
    ctx = myCanvas.getContext("2d")
    myCanvas.width = window.innerWidth
    myCanvas.height = window.innerHeight

    // Push stars to array
    for (let i = 0; i < x; i++) {
      stars.push({
        x: Math.random() * myCanvas.width,
        y: Math.random() * myCanvas.height,
        radius: Math.random() * 1 + 1,
        vx: Math.floor(Math.random() * 50) - 25,
        vy: Math.floor(Math.random() * 50) - 25,
      })
    }

    myCanvas.addEventListener("mousemove", function (e) {
      mouse.x = e.clientX
      mouse.y = e.clientY
    })
  })

  function draw() {
    if (!ctx || !myCanvas) return
    ctx.clearRect(0, 0, myCanvas.width, myCanvas.height)

    ctx.globalCompositeOperation = "lighter"

    for (var i = 0, x = stars.length; i < x; i++) {
      var s = stars[i]

      ctx.fillStyle = "#F6B17A"
      ctx.beginPath()
      ctx.arc(s.x, s.y, s.radius, 0, 2 * Math.PI)
      ctx.fill()
      ctx.fillStyle = "black"
      ctx.stroke()
    }
  }

  // Update star locations

  function update() {
    if (!myCanvas) return
    for (var i = 0, x = stars.length; i < x; i++) {
      var s = stars[i]

      s.x += s.vx / FPS
      s.y += s.vy / FPS

      if (s.x < 0 || s.x > myCanvas.width) s.vx = -s.vx
      if (s.y < 0 || s.y > myCanvas.height) s.vy = -s.vy
    }
  }

  // Update and draw

  function tick() {
    draw()
    update()
    requestAnimationFrame(tick)
  }

  tick()
</script>

<div class="canvas-bg">
  <div class="canvas">
    <canvas bind:this={myCanvas}></canvas>
  </div>
</div>

<style>
  .canvas-bg {
    position: fixed;
    top: 0;
    width: 100%;
    background-color: royalblue;
  }

  .canvas {
    top: 0;
    right: 0;
    left: 0;
    bottom: 0;
    width: 100%;
    background-color: #424769;
    overflow: hidden;
  }

  canvas {
    height: 100vh;
    z-index: 999;
  }
</style>
