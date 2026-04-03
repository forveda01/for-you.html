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
  height:100vh;
  display:flex;
  justify-content:center;
  align-items:center;
  background:black;
  overflow:hidden;
  color:white;
}

/* 🌌 Stars */
.stars{
  position:absolute;
  width:100%;
  height:100%;
  z-index:0;
}

.star{
  position:absolute;
  width:2px;
  height:2px;
  background:white;
  border-radius:50%;
  opacity:0.7;
  animation:twinkle 3s infinite ease-in-out;
}

@keyframes twinkle{
  0%,100%{opacity:0.2;}
  50%{opacity:1;}
}

/* 💎 Container */
.container{
  position:relative;
  z-index:2;
  text-align:center;
  padding:20px;
  max-width:800px;
  animation:fadeIn 2s ease;
}

@keyframes fadeIn{
  from{opacity:0; transform:scale(0.95);}
  to{opacity:1; transform:scale(1);}
}

/* ✨ Main */
.main{
  font-family:'Playfair Display',serif;
  font-size:65px;
  margin-bottom:30px;

  background:linear-gradient(90deg,#ffffff,#d1d5db,#ffffff);
  -webkit-background-clip:text;
  -webkit-text-fill-color:transparent;

  text-shadow:0 0 25px rgba(255,255,255,0.3);

  animation:slideUp 1.5s ease forwards;
}

/* 💖 Lines */
.line{
  font-family:'Poppins',sans-serif;
  font-size:28px;
  margin:16px 0;
  opacity:0;
  animation:slideUp 1.5s forwards;
  color:#e5e7eb;
}

/* 🎬 Animation */
@keyframes slideUp{
  from{
    opacity:0;
    transform:translateY(40px);
  }
  to{
    opacity:1;
    transform:translateY(0);
  }
}

/* 📱 Mobile */
@media(max-width:500px){
  .main{font-size:42px;}
  .line{font-size:20px;}
}

</style>
</head>

<body>

<div class="stars" id="stars"></div>

<div class="container">

<div class="main">
Good Morning Veda ❤️
</div>

<div class="line" style="animation-delay:1s;">
Keep smiling… don’t let anyone ruin it 🙂
</div>

<div class="line" style="animation-delay:2s;">
Some days feel heavier, but they pass too.
</div>

<div class="line" style="animation-delay:3s;">
You don’t have to figure everything out all at once.
</div>

<div class="line" style="animation-delay:4s;">
Hope your day goes really well
</div>

</div>

<script>

/* 🌠 Stars */
for(let i=0;i<100;i++){
  let star=document.createElement("div");
  star.className="star";
  star.style.top=Math.random()*100+"vh";
  star.style.left=Math.random()*100+"vw";
  star.style.animationDuration=(Math.random()*3+2)+"s";
  document.getElementById("stars").appendChild(star);
}

</script>

</body>
</html>
