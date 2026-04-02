<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>For You 🌸</title>

<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  min-height: 100vh;
  font-family: 'Poppins', sans-serif;

  overflow-x: hidden;
  overflow-y: auto;

  display: flex;
  justify-content: center;
  align-items: flex-start;

  padding: 40px 0;

  background: linear-gradient(-45deg, #ff9a9e, #fad0c4, #fbc2eb, #a18cd1);
  background-size: 400% 400%;
  animation: gradientBG 12s ease infinite;
}

@keyframes gradientBG {
  0% {background-position:0% 50%;}
  50% {background-position:100% 50%;}
  100% {background-position:0% 50%;}
}

/* intro */
#intro {
  position: fixed;
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  color: white;
  font-size: 2rem;
  text-align: center;
  background: rgba(0,0,0,0.3);
  z-index: 10;
  animation: fadeOut 3s forwards;
  animation-delay: 2.5s;
}

@keyframes fadeOut {
  to {opacity: 0; visibility: hidden;}
}

/* card */
.card {
  position: relative;
  padding: 35px;
  text-align: center;

  background: rgba(255,255,255,0.25);
  border-radius: 20px;
  box-shadow: 0 8px 30px rgba(0,0,0,0.2);
  color: white;

  width: 92%;
  max-width: 550px;

  max-height: 85vh;
  overflow-y: auto;

  transition: transform 0.3s ease;
}

.card:hover {
  transform: scale(1.02);
}

h1 {
  color: #ff4d6d;
}

.sub {
  font-size: 0.85rem;
  opacity: 0.8;
  margin-bottom: 15px;
}

/* text animation */
.line {
  opacity: 0;
  transform: translateY(10px);
  animation: fadeUp 0.8s forwards;
}

@keyframes fadeUp {
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

/* buttons */
.btn {
  margin-top: 10px;
  padding: 10px 18px;
  border: none;
  border-radius: 25px;
  cursor: pointer;
  font-weight: 600;
}

.yes {
  background: #ff4d6d;
  color: white;
}

.no {
  background: white;
  color: #333;
  position: relative;
}

#result {
  margin-top: 20px;
  line-height: 1.5;
}

/* floating hearts */
.float-heart {
  position: fixed;
  bottom: -20px;
  font-size: 16px;
  animation: rise 6s linear forwards;
}

@keyframes rise {
  to {transform: translateY(-110vh);}
}

/* click hearts */
.heart {
  position: fixed;
  font-size: 18px;
  animation: explode 0.8s ease forwards;
}

@keyframes explode {
  to {
    opacity: 0;
    transform: translate(var(--x), var(--y));
  }
}
</style>
</head>

<body>

<div id="intro">
  For you 🌸<br><small style="font-size:1rem;">wait a second...</small>
</div>

<div class="card" id="card">

  <h1>For You 🌸</h1>
  <div class="sub">open this slowly...</div>

  <div id="text"></div>

  <div style="margin-top:20px; position: relative; height: 90px;">
    <p><b>Did this make you feel special? 😊</b></p>

    <div style="margin-top:10px;">
      <button class="btn yes" onclick="yesClick(event)">Yes 💖</button>
      <button class="btn no" id="noBtn">No 😅</button>
    </div>
  </div>

  <div id="result"></div>

</div>

<script>

// show text after intro
setTimeout(showText, 2800);

// text lines
const lines = [
  "Good morning Veda ❤️",
  "I don’t know why… but I felt like writing this.",
  "You’re actually a really good human being.",
  "The way you think… it’s rare.",
  "And honestly… not everyone has that.",
  "There’s something about your vibe,",
  "it’s calm… a little different…",
  "and yeah… kinda addictive 🥺",
  "Not gonna lie… talking to you feels different.",
  "In a way I didn’t expect.",
  "And maybe that’s what makes it special.",
  "✨ Keep smiling ✨",
  "Because it actually changes the vibe around you.",
  "So yeah… just stay the way you are."
];

function showText(){
  let container=document.getElementById("text");

  lines.forEach((line,i)=>{
    let p=document.createElement("p");
    p.className="line";
    p.style.animationDelay=(i*0.5)+"s";
    p.innerHTML=line;
    container.appendChild(p);

    setTimeout(()=>{
      container.scrollTop = container.scrollHeight;
    }, i*500);
  });
}

// floating hearts (optimized)
setInterval(()=>{
  let hearts = document.querySelectorAll(".float-heart");
  if (hearts.length > 10) return;

  let h=document.createElement("div");
  h.className="float-heart";
  h.innerHTML="❤️";
  h.style.left=Math.random()*100+"vw";
  document.body.appendChild(h);

  setTimeout(()=>h.remove(),6000);
},1500);

// YES click
function yesClick(e){
  document.getElementById("result").innerHTML =
  "That’s all I wanted 💖<br><br>...and yeah, I meant what I said that day.";

  for(let i=0;i<10;i++){
    let heart=document.createElement("div");
    heart.className="heart";
    heart.innerHTML="❤️";

    let x=(Math.random()-0.5)*150+"px";
    let y=(Math.random()-0.5)*150+"px";

    heart.style.setProperty('--x',x);
    heart.style.setProperty('--y',y);

    heart.style.left=e.clientX+"px";
    heart.style.top=e.clientY+"px";

    document.body.appendChild(heart);
    setTimeout(()=>heart.remove(),800);
  }
}

// NO button movement
let noBtn=document.getElementById("noBtn");
noBtn.addEventListener("mouseover",()=>{
  noBtn.style.position="absolute";
  noBtn.style.left=Math.random()*70+"%";
  noBtn.style.top=Math.random()*40+"%";
});

</script>

</body>
</html>
