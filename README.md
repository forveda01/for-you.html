<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>For You</title>

<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@500;700&family=Inter:wght@300;400&display=swap" rel="stylesheet">

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
}

.star{
  position:absolute;
  width:2px;
  height:2px;
  background:white;
  opacity:0.7;
  animation:twinkle 2s infinite ease-in-out;
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
  max-width:90%;
}

/* ✨ Main Heading */
.main{
  font-family:'Playfair Display',serif;
  font-size:34px;
  margin-bottom:20px;
  opacity:0;
  animation:fadeUp 1s forwards;
}

/* 💖 Highlight line */
.highlight{
  font-family:'Playfair Display',serif;
  font-size:36px;
  font-weight:700;
  margin:20px 0;
  opacity:0;
  animation:fadeUp 1s forwards;
  color:#ffffff;

  text-shadow:
    0 0 8px rgba(255,255,255,0.8),
    0 0 20px rgba(255,255,255,0.6),
    0 0 35px rgba(255,255,255,0.4);
}

/* ✍ Normal lines */
.line{
  font-family:'Inter',sans-serif;
  font-size:18px;
  margin:10px 0;
  opacity:0.85;
  opacity:0;
  animation:fadeUp 1s forwards;
}

/* ✨ Animation */
@keyframes fadeUp{
  from{
    opacity:0;
    transform:translateY(20px);
  }
  to{
    opacity:1;
    transform:translateY(0);
  }
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

/* ⭐ Stars generator */
for(let i=0;i<100;i++){
  let star=document.createElement("div");
  star.className="star";
  star.style.top=Math.random()*100+"vh";
  star.style.left=Math.random()*100+"vw";
  star.style.animationDuration=(Math.random()*3+1)+"s";
  document.getElementById("stars").appendChild(star);
}

</script>

</body>
</html>
