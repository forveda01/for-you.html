<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>For You</title>

<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;500&display=swap" rel="stylesheet">

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
  font-family:'Poppins',sans-serif;
}

/* ✨ Stars Background */
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
  opacity:0.8;
  animation:twinkle 2s infinite ease-in-out;
}

@keyframes twinkle{
  0%,100%{opacity:0.2;}
  50%{opacity:1;}
}

/* 💎 Text Container */
.container{
  position:relative;
  z-index:2;
  text-align:center;
  padding:30px;
}

/* ✨ Shiny Text */
.line{
  color:white;
  font-size:22px;
  margin:12px 0;
  opacity:0;
  transform:translateY(20px);
  animation:fadeUp 1s forwards;
  text-shadow:0 0 10px rgba(255,255,255,0.8),
              0 0 20px rgba(255,255,255,0.5);
}

@keyframes fadeUp{
  to{
    opacity:1;
    transform:translateY(0);
  }
}

/* 💫 Slight Glow Highlight */
.highlight{
  font-weight:500;
  text-shadow:0 0 15px #fff, 0 0 30px #aaa;
}

</style>
</head>

<body>

<!-- Stars -->
<div class="stars" id="stars"></div>

<!-- Content -->
<div class="container" id="text"></div>

<script>

/* ⭐ Create Stars */
for(let i=0;i<120;i++){
  let star=document.createElement("div");
  star.className="star";
  star.style.top=Math.random()*100+"vh";
  star.style.left=Math.random()*100+"vw";
  star.style.animationDuration=(Math.random()*3+1)+"s";
  document.getElementById("stars").appendChild(star);
}

/* 💬 Text Lines (ELITE VERSION) */
const lines=[
"Good morning Veda",

"<span class='highlight'>Keep smiling… it suits you 🙂</span>",

"Your smile is worth more than you think.",
"Don’t let anyone take that away from you.",

"And… don’t overthink things too much,",
"not everything really deserves space in your mind.",

"Some things are better felt…",
"than figured out."
];

/* ✨ Show text one by one */
let container=document.getElementById("text");

lines.forEach((line,i)=>{
  let p=document.createElement("div");
  p.className="line";
  p.style.animationDelay=(i*1)+"s";
  p.innerHTML=line;
  container.appendChild(p);
});

</script>

</body>
</html>
