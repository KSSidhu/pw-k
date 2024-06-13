<script lang="ts">
  import { onMount } from "svelte"

  type Point = {
    x: number
    y: number
  }

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

  // Draw the scene

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

    ctx.beginPath()
    for (var i = 0, x = stars.length; i < x; i++) {
      var starI = stars[i]
      ctx.moveTo(starI.x, starI.y)
      if (distance(mouse, starI) < 150) ctx.lineTo(mouse.x, mouse.y)
      for (var j = 0, x = stars.length; j < x; j++) {
        var starII = stars[j]
        if (distance(starI, starII) < 150) {
          //ctx.globalAlpha = (1 / 150 * distance(starI, starII).toFixed(1));
          ctx.lineTo(starII.x, starII.y)
        }
      }
    }
    ctx.lineWidth = 0.05
    ctx.strokeStyle = "white"
    ctx.stroke()
  }

  function distance(point1: Point, point2: Star) {
    var xs = 0
    var ys = 0

    xs = point2.x - point1.x
    xs = xs * xs

    ys = point2.y - point1.y
    ys = ys * ys

    return Math.sqrt(xs + ys)
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

<section id="hero" class="hero">
  <canvas bind:this={myCanvas}></canvas>

  <div class="heading">
    <h1><span>Kirat Sidhu </span> | Full Stack Developer</h1>

    <a href="#about" class="button">Nice to meet you!</a>
  </div>
</section>

<style>
  section {
    position: relative;
    z-index: 999;
  }

  canvas {
    background: #424769;
    position: absolute;
    height: 100vh;
    width: 100%;
    top: 0;
    bottom: 0;
    right: 0;
    left: 0;
  }

  span {
    color: #f6b17a;
  }

  h1 {
    font-size: 4em;
    font-weight: 400;
  }

  a {
    text-decoration: none;
    color: #f6b17a;
    font-size: 2em;
    border: 1px solid #f6b17a;
    border-radius: 8px;
    padding: 0.25em 0.5em;

    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    z-index: -1;
    content: "";
    transition: transform 0.3s;
    position: relative;
    display: inline-block;
  }

  a::before {
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    z-index: -1;
    content: "";
    background: #f6b17a;
    transition: transform 0.3s;
  }

  a:hover {
    color: white;
    transition: transform 0.3s;
  }

  .button::before {
    transform-origin: left bottom;
    transform: scale(1, 0);
  }

  .button:hover::before {
    transform-origin: left top;
    transform: scale(1, 1);
  }

  .hero {
    display: flex;
    height: 100vh;
    width: 100%;
  }

  .heading {
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    z-index: 999;
    margin-left: auto;
    margin-right: auto;
  }
</style>
