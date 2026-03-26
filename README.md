<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<title>Para CHELAINI 💛</title>

<style>
body {
  margin: 0;
  overflow: hidden;
  background: black;
  font-family: Arial;
}

/* Pantalla inicial */
.start {
  position: fixed;
  width: 100%;
  height: 100%;
  background: black;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  color: gold;
  font-size: 35px;
  z-index: 10;
  cursor: pointer;
}

.start span {
  font-size: 45px;
}

/* Escena */
.scene {
  display: none;
  perspective: 900px;
  width: 100%;
  height: 100%;
}

.galaxy {
  width: 100%;
  height: 100%;
  transform-style: preserve-3d;
  animation: rotar 30s linear infinite;
}

@keyframes rotar {
  from { transform: rotateY(0deg); }
  to { transform: rotateY(360deg); }
}

/* Estrellas */
.star {
  position: absolute;
  width: 2px;
  height: 2px;
  background: gold;
  border-radius: 50%;
}

/* Flores */
.flower {
  position: absolute;
  width: 30px;
}

/* Centro brillante */
.center {
  position: absolute;
  top: 50%;
  left: 50%;
  width: 250px;
  height: 250px;
  background: radial-gradient(circle, gold, transparent);
  transform: translate(-50%, -50%);
  border-radius: 50%;
  box-shadow: 0 0 80px gold;
}

/* Texto */
h1 {
  position: absolute;
  top: 10%;
  width: 100%;
  text-align: center;
  color: gold;
  font-size: 45px;
  text-shadow: 0 0 25px gold;
}

/* Ramo */
.bouquet {
  position: absolute;
  bottom: 10%;
  left: 50%;
  transform: translateX(-50%);
  width: 150px;
  opacity: 0;
  transition: 2s;
}
</style>
</head>

<body>

<!-- Inicio -->
<div class="start" onclick="iniciar()">
  Toca aquí  
  <span>Para CHELAINI 💛</span>
</div>

<!-- Escena -->
<div class="scene" id="scene">
  <h1>Para CHELAINI 💛</h1>
  <div class="galaxy" id="galaxy"></div>
  <div class="center"></div>

  <!-- Ramo -->
  <img class="bouquet" id="ramo" src="https://i.imgur.com/6XKQF6T.png">
</div>

<script>
let galaxy = document.getElementById("galaxy");

/* Iniciar */
function iniciar() {
  document.querySelector(".start").style.display = "none";
  document.getElementById("scene").style.display = "block";

  setTimeout(() => {
    document.getElementById("ramo").style.opacity = "1";
  }, 2000);
}

/* Estrellas */
for (let i = 0; i < 200; i++) {
  let s = document.createElement("div");
  s.className = "star";
  s.style.left = Math.random()*100 + "%";
  s.style.top = Math.random()*100 + "%";
  s.style.transform = "translateZ(" + (Math.random()*600) + "px)";
  galaxy.appendChild(s);
}

/* Flores reales (imagen) */
for (let i = 0; i < 60; i++) {
  let f = document.createElement("img");
  f.src = "https://i.imgur.com/8pQZ6Kk.png";
  f.className = "flower";

  f.style.left = Math.random()*100 + "%";
  f.style.top = Math.random()*100 + "%";
  f.style.transform = "translateZ(" + (Math.random()*500) + "px)";
  
  galaxy.appendChild(f);
}

/* Mensajes */
let mensajes = [
  "Eres especial 💛",
  "Siempre contigo ✨",
  "Para ti 🌻",
  "Eres única 💫",
  "Mi persona favorita 💛"
];

for (let i = 0; i < 40; i++) {
  let t = document.createElement("div");
  t.innerHTML = mensajes[Math.floor(Math.random()*mensajes.length)];

  t.style.position = "absolute";
  t.style.color = "gold";
  t.style.fontSize = "14px";

  t.style.left = Math.random()*100 + "%";
  t.style.top = Math.random()*100 + "%";
  t.style.transform = "translateZ(" + (Math.random()*500) + "px)";

  galaxy.appendChild(t);
}
</script>

</body>
</html>
