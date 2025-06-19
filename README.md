<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Mandeep Run</title>
  <style>
    body {
      margin: 0;
      overflow: hidden;
      background: url('https://i.imgur.com/7HgbF3E.png') repeat-x;
      background-size: cover;
    }
    canvas {
      display: block;
      margin: 0 auto;
      background: transparent;
    }
  </style>
</head>
<body>
<canvas id="game" width="400" height="600"></canvas>

<script>
const canvas = document.getElementById("game");
const ctx = canvas.getContext("2d");

let boy = { x: 180, y: 500, width: 40, height: 40, speed: 5 };
let coins = [];
let score = 0;

function drawBoy() {
  ctx.fillStyle = "blue";
  ctx.fillRect(boy.x, boy.y, boy.width, boy.height);
}

function drawCoins() {
  ctx.fillStyle = "gold";
  coins.forEach(c => {
    ctx.beginPath();
    ctx.arc(c.x, c.y, 10, 0, Math.PI * 2);
    ctx.fill();
  });
}

function updateCoins() {
  coins.forEach(c => c.y += 3);
  coins = coins.filter(c => c.y < canvas.height);
}

function checkCollision() {
  coins.forEach((c, i) => {
    if (
      c.x > boy.x &&
      c.x < boy.x + boy.width &&
      c.y > boy.y &&
      c.y < boy.y + boy.height
    ) {
      coins.splice(i, 1);
      score += 1;
    }
  });
}

function gameLoop() {
  ctx.clearRect(0, 0, canvas.width, canvas.height);

  drawBoy();
  drawCoins();
  updateCoins();
  checkCollision();

  ctx.fillStyle = "white";
  ctx.font = "20px Arial";
  ctx.fillText("Score: " + score, 10, 30);

  requestAnimationFrame(gameLoop);
}

document.addEventListener("keydown", e => {
  if (e.key === "ArrowLeft" && boy.x > 0) boy.x -= boy.speed;
  if (e.key === "ArrowRight" && boy.x < canvas.width - boy.width) boy.x += boy.speed;
});

setInterval(() => {
  let x = Math.random() * (canvas.width - 20) + 10;
  coins.push({ x, y: 0 });
}, 1000);

gameLoop();
</script>
</body>
</html><!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Mandeep Run</title>
  <style>
    body {
      margin: 0;
      overflow: hidden;
      background: url('https://i.imgur.com/7HgbF3E.png') repeat-x;
      background-size: cover;
    }
    canvas {
      display: block;
      margin: 0 auto;
      background: transparent;
    }
  </style>
</head>
<body>
<canvas id="game" width="400" height="600"></canvas>

<script>
const canvas = document.getElementById("game");
const ctx = canvas.getContext("2d");

let boy = { x: 180, y: 500, width: 40, height: 40, speed: 5 };
let coins = [];
let score = 0;

function drawBoy() {
  ctx.fillStyle = "blue";
  ctx.fillRect(boy.x, boy.y, boy.width, boy.height);
}

function drawCoins() {
  ctx.fillStyle = "gold";
  coins.forEach(c => {
    ctx.beginPath();
    ctx.arc(c.x, c.y, 10, 0, Math.PI * 2);
    ctx.fill();
  });
}

function updateCoins() {
  coins.forEach(c => c.y += 3);
  coins = coins.filter(c => c.y < canvas.height);
}

function checkCollision() {
  coins.forEach((c, i) => {
    if (
      c.x > boy.x &&
      c.x < boy.x + boy.width &&
      c.y > boy.y &&
      c.y < boy.y + boy.height
    ) {
      coins.splice(i, 1);
      score += 1;
    }
  });
}

function gameLoop() {
  ctx.clearRect(0, 0, canvas.width, canvas.height);

  drawBoy();
  drawCoins();
  updateCoins();
  checkCollision();

  ctx.fillStyle = "white";
  ctx.font = "20px Arial";
  ctx.fillText("Score: " + score, 10, 30);

  requestAnimationFrame(gameLoop);
}

document.addEventListener("keydown", e => {
  if (e.key === "ArrowLeft" && boy.x > 0) boy.x -= boy.speed;
  if (e.key === "ArrowRight" && boy.x < canvas.width - boy.width) boy.x += boy.speed;
});

setInterval(() => {
  let x = Math.random() * (canvas.width - 20) + 10;
  coins.push({ x, y: 0 });
}, 1000);

gameLoop();
</script>
</body>
</html# MANDEEP-RUN-
To play 
