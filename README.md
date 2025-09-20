# Flores-amarillas-
Para mí niña 
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Para Mari Cielo - Ramo de Flores Amarillas</title>
<style>
  body {
    margin: 0;
    height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    background: linear-gradient(to top, #fdf6e3, #fff);
    overflow: hidden;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  }
  h1 {
    color: #d4af37;
    font-size: 2.5em;
    text-shadow: 2px 2px 4px rgba(0,0,0,0.2);
    margin-bottom: 20px;
    animation: float 3s ease-in-out infinite;
  }
  @keyframes float {
    0%, 100% { transform: translateY(0px); }
    50% { transform: translateY(-10px); }
  }
  canvas {
    border: none;
  }
  button {
    margin-top: 20px;
    padding: 10px 20px;
    background: #ffd700;
    border: none;
    border-radius: 25px;
    font-size: 1em;
    cursor: pointer;
    box-shadow: 0 4px 6px rgba(0,0,0,0.2);
  }
</style>
</head>
<body>
  <h1>Para Mari Cielo</h1>
  <canvas id="ramo" width="400" height="400"></canvas>
  <button onclick="playMusic()">🔊 Reproducir canción</button>
  <audio id="musica" autoplay loop>
    <source src="flores.mp3" type="audio/mpeg">
    Tu navegador no soporta audio.
  </audio>
<script>
const canvas = document.getElementById('ramo');
const ctx = canvas.getContext('2d');

// Dibujar tallos
function drawStems() {
  ctx.strokeStyle = "#228B22";
  ctx.lineWidth = 4;
  for (let i = 0; i < 7; i++) {
    ctx.beginPath();
    ctx.moveTo(200, 400);
    ctx.lineTo(150 + i*20, 250);
    ctx.stroke();
  }
}

// Dibujar una flor
function drawFlower(x, y, scale, angle) {
  ctx.save();
  ctx.translate(x, y);
  ctx.rotate(angle);
  ctx.scale(scale, scale);
  // pétalos
  for (let i = 0; i < 8; i++) {
    ctx.rotate(Math.PI / 4);
    let gradient = ctx.createRadialGradient(
