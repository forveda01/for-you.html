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
  height: 100vh;
  font-family: 'Poppins', sans-serif;
  overflow: hidden;
  background: linear-gradient(-45deg, #ff9a9e, #fad0c4, #fbc2eb, #a18cd1);
  background-size: 400% 400%;
  animation: gradientBG 10s ease infinite;
}

@keyframes gradientBG {
  0% {background-position:0% 50%;}
  50% {background-position:100% 50%;}
  100% {background-position:0% 50%;}
}

/* intro screen */
#intro {
  position: absolute;
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  color: white;
  font-size: 2rem;
  text-align: center;
  animation: fadeOut 3s forwards;
  animation-delay: 2.5s;
}

@keyframes fadeOut {
  to {opacity: 0; visibility: hidden;}
}

/* main card */
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100%;
}

.card {
  padding: 30px;
  text-align: center;
  background: rgba(255,255,255,0.2);
  border-radius: 20px;
  backdrop-filter: blur(15px);
  box-shadow: 0 8px 30px rgba(0,0,0,0.2);
  color: white;
  max-width: 350px;
  display: none;
}

h1 { color: #ff6f91; }

.sub {
  font-size: 0.85rem;
  opacity: 0.8;
  margin-bottom: 15px;
}

.text p {
  margin: 6px 0;
  font-size: 0.95rem;
}

.highlight {
  color: #ff6f91;
  font-weight: 600;
}

.btn {
  margin-top: 15px;
  padding: 10px 18px;
  border: none;
  border-radius: 25px;
  cursor: pointer;
  font-weight: 600;
}

.yes {
  background: #ff6f91;
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

/* hearts */
.heart {
  position: absolute;
  font-size: 20px;
  animation: explode 1s ease forwards;
}

@keyframes explode {
  0% {opacity:1;}
  100% {opacity:0; transform: translate(var(--x), var(--y));}
}

/* floating hearts */
.float-heart {
  position: absolute;
  bottom: -20px;
  font-size: 18px;
  animation: rise 6s linear infinite;
}

@keyframes rise {
  to {transform: translateY(-110vh);}
}
</style>
</head>

<body>

<!-- INTRO -->
<div id="intro">
  For Veda 🌸<br><small style="font-size:1rem;">wait a second...</small>
</div>

<div class="container">
<div class="card" id="card">

  <h1>For You 🌸</h1>
  <div class="sub">open this slowly...</div>

  <div class="text">

    <p><b>Good morning Veda ❤️</b></p><br>

    <p>You’re actually a really good human being.</p>
    <p>The way you think... it’s rare.</p><br>

    <p>There’s something about your vibe,</p>
    <p>it’s calm... and kinda addictive 🥺</p><br>

    <p style="opacity:0.9;">Not gonna lie... talking to you feels different.</p><br>

    <p class="highlight">✨ Keep smiling ✨</p>

  </div>

  <p style="margin-top:15px;"><b>Did this make you feel special? 😊</b></p>

  <button class="btn yes" onclick="yesClick(event)">Yes 💖</button>
  <button class="btn no" id="noBtn">No 😅</button>

  <div id="result"></div>

</div>
</div>

<script>
// show card after intro
setTimeout(() => {
  document.getElementById("card").style.display = "block";
}, 2800);

// floating hearts
setInterval(()=>{
  let h=document.createElement("div");
  h.className="float-heart";
  h.innerHTML="❤️";
  h.style.left=Math.random()*100+"vw";
  document.body.appendChild(h);
  setTimeout(()=>h.remove(),6000);
},800);

// YES click
function yesClick(e){
  document.getElementById("result").innerHTML =
  "That’s all I wanted 💖<br><br>...and yeah, I meant what I said that day.<br><br><b>Maybe this is just the beginning ✨</b>";

  for(let i=0;i<20;i++){
    let heart=document.createElement("div");
    heart.className="heart";
    heart.innerHTML="❤️";

    let x=(Math.random()-0.5)*200+"px";
    let y=(Math.random()-0.5)*200+"px";

    heart.style.setProperty('--x',x);
    heart.style.setProperty('--y',y);

    heart.style.left=e.clientX+"px";
    heart.style.top=e.clientY+"px";

    document.body.appendChild(heart);
    setTimeout(()=>heart.remove(),1000);
  }
}

// NO button runs away
let noBtn = document.getElementById("noBtn");

noBtn.addEventListener("mouseover", () => {
  noBtn.style.position = "absolute";
  noBtn.style.left = Math.random() * 80 + "%";
  noBtn.style.top = Math.random() * 80 + "%";
});
</script>

</body>
</html>
