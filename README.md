<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>For You</title>

<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@500;700&family=Inter:wght@300;400&display=swap" rel="stylesheet">

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
  background:#000;
  overflow:hidden;
  color:white;
}

/* 🌌 Background Stars */
.stars{
  position:absolute;
  width:100%;
  height:100%;
  overflow:hidden;
  z-index:0;
}

.star{
  position:absolute;
  width:2px;
  height:2px;
  background:white;
  border-radius:50%;
  opacity:0.5;
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
  max-width:700px;
  padding:20px;
  animation:zoomIn 3s ease;
}

@keyframes zoomIn{
  from{transform:scale(0.95);}
  to{transform:scale(1);}
}

/* ✨ Heading */
.main{
  font-family:'Cormorant Garamond',serif;
  font-size:40px;
  margin-bottom:25px;
  letter-spacing:1px;
  opacity:0;
  animation:fadeUp 1s forwards;
}

/* 💖 Hero line */
.highlight{
  font-family:'Cormorant Garamond',serif;
  font-size:48px;
  font-weight:700;
  margin:20px 0;
  opacity:0;
  animation:fadeUp 1s forwards;

  background:linear-gradient(90deg,#ffffff,#d1d5db,#ffffff);
  -webkit-background-clip:text;
  -webkit-text-fill-color:transparent;

  text-shadow:0 0 20px rgba(255,255,255,0.35);
}

/* ✍ Other lines */
.line{
  font-family:'Inter',sans-serif;
  font-size:19px;
  margin:10px 0;
  opacity:0;
  animation:fadeUp 1s forwards;
  color:#d1d5db;
}

/* 🎬 Animation */
@keyframes fadeUp{
  from{
    opacity:0;
    transform:translateY(25px);
  }
  to{
    opacity:1;
    transform:translateY(0);
  }
}

/* 📱 Mobile Fix */
@media(max-width:500px){
  .main{font-size:30px;}
  .highlight{font-size:34px;}
  .line{font-size:16px;}
}

</style>
</head>

<body>

<div class="stars" id="stars"></div>

<div class="container">

<div class="main" style="animation-delay:0.5s;">
Good morning Veda
</div>

<div class="highlight" style="animation-delay:1.5s;">
Keep smiling… it suits you 🙂
</div>

<div class="line" style="animation-delay:2.5s;">
Your smile is worth more than you think.
</div>

<div class="line" style="animation-delay:3.5s;">
Don’t let anyone take that away from you.
</div>

<div class="line" style="animation-delay:4.5s;">
And… don’t overthink things too much,
</div>

<div class="line" style="animation-delay:5.5s;">
not everything really deserves space in your mind.
</div>

<div class="line" style="animation-delay:6.5s;">
Some things are better felt…
</div>

<div class="line" style="animation-delay:7.5s;">
than figured out.
</div>

</div>

<script>

/* 🌠 Better Stars */
for(let i=0;i<120;i++){
  let star=document.createElement("div");
  star.className="star";
  star.style.top=Math.random()*100+"vh";
  star.style.left=Math.random()*100+"vw";
  star.style.animationDuration=(Math.random()*4+2)+"s";
  document.getElementById("stars").appendChild(star);
}

</script>

</body>
</html>
