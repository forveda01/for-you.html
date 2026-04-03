<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>For You</title>

<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@600;700&family=Poppins:wght@300;400&display=swap" rel="stylesheet">

<style>
*{
  margin:0;
  padding:0;
  box-sizing:border-box;
}

body{
  min-height:100vh;
  display:flex;
  justify-content:center;
  align-items:center;
  background:#000;
  overflow:hidden;
  color:white;
  font-family:'Poppins',sans-serif;
}

/* 🌌 STAR LAYERS */
.stars, .stars2, .stars3{
  position:absolute;
  width:100%;
  height:100%;
}

.star{
  position:absolute;
  background:white;
  border-radius:50%;
}

/* Layer 1 */
.stars .star{
  width:2px;
  height:2px;
  opacity:0.6;
  animation:twinkle 3s infinite;
}

/* Layer 2 */
.stars2 .star{
  width:3px;
  height:3px;
  opacity:0.4;
  animation:twinkle 5s infinite;
}

/* Layer 3 */
.stars3 .star{
  width:1px;
  height:1px;
  opacity:0.3;
  animation:twinkle 7s infinite;
}

@keyframes twinkle{
  0%,100%{opacity:0.2;}
  50%{opacity:1;}
}

/* 💎 GLASS CARD */
.container{
  position:relative;
  z-index:2;
  text-align:center;
  padding:40px 30px;
  max-width:700px;
  width:90%;

  border-radius:25px;

  background:rgba(255,255,255,0.05);
  backdrop-filter:blur(15px);

  box-shadow:
    0 0 40px rgba(255,255,255,0.08),
    0 0 80px rgba(255,255,255,0.05);

  animation:float 6s ease-in-out infinite;
}

@keyframes float{
  0%,100%{transform:translateY(0);}
  50%{transform:translateY(-10px);}
}

/* ✨ TEXT */
.main{
  font-family:'Playfair Display',serif;
  font-size:58px;
  margin-bottom:25px;

  background:linear-gradient(90deg,#fff,#ddd,#fff);
  -webkit-background-clip:text;
  -webkit-text-fill-color:transparent;

  text-shadow:0 0 25px rgba(255,255,255,0.25);

  opacity:0;
  animation:fadeUp 1s forwards;
}

.line{
  font-size:24px;
  margin:14px 0;
  color:#e5e7eb;

  opacity:0;
  animation:fadeUp 1s forwards;
}

/* 🎬 Animation */
@keyframes fadeUp{
  from{
    opacity:0;
    transform:translateY(30px);
  }
  to{
    opacity:1;
    transform:translateY(0);
  }
}

/* 📱 Mobile */
@media(max-width:500px){
  .main{font-size:36px;}
  .line{font-size:18px;}
  .container{padding:25px;}
}

</style>
</head>

<body>

<div class="stars" id="stars"></div>
<div class="stars2" id="stars2"></div>
<div class="stars3" id="stars3"></div>

<div class="container">

<div class="main" style="animation-delay:0.5s;">
Good Morning Veda ❤️
</div>

<div class="line" style="animation-delay:1.5s;">
Keep smiling… don’t let anyone ruin it 🙂
</div>

<div class="line" style="animation-delay:2.5s;">
Some days feel heavy, but they pass too.
</div>

<div class="line" style="animation-delay:3.5s;">
You don’t have to figure everything out at once.
</div>

<div class="line" style="animation-delay:4.5s;">
Hope your day goes really well
</div>

</div>

<script>

/* 🌠 Generate stars */
function createStars(container, count){
  for(let i=0;i<count;i++){
    let star=document.createElement("div");
    star.className="star";
    star.style.top=Math.random()*100+"vh";
    star.style.left=Math.random()*100+"vw";
    container.appendChild(star);
  }
}

createStars(document.getElementById("stars"),60);
createStars(document.getElementById("stars2"),40);
createStars(document.getElementById("stars3"),30);

</script>

</body>
</html>
