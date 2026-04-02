<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>For You 🌸</title>

<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">

<style>
*{margin:0;padding:0;box-sizing:border-box;}

body{
  min-height:100vh;
  font-family:'Poppins',sans-serif;
  display:flex;
  justify-content:center;
  align-items:flex-start;
  padding:40px 0;
  overflow-x:hidden;

  background:linear-gradient(-45deg,#ff9a9e,#fad0c4,#fbc2eb,#a18cd1);
  background-size:400% 400%;
  animation:gradientBG 12s ease infinite;
}

@keyframes gradientBG{
  0%{background-position:0% 50%;}
  50%{background-position:100% 50%;}
  100%{background-position:0% 50%;}
}

#intro{
  position:fixed;
  width:100%;
  height:100%;
  display:flex;
  justify-content:center;
  align-items:center;
  color:white;
  font-size:2rem;
  text-align:center;
  background:rgba(0,0,0,0.3);
  z-index:10;
  animation:fadeOut 3s forwards;
  animation-delay:2.5s;
}
@keyframes fadeOut{to{opacity:0;visibility:hidden;}}

.card{
  padding:35px;
  text-align:center;
  background:rgba(255,255,255,0.25);
  border-radius:20px;
  box-shadow:0 8px 30px rgba(0,0,0,0.2);
  color:white;
  width:92%;
  max-width:550px;
  max-height:85vh;
  overflow-y:auto;
}

h1{color:#ff4d6d;}

.line{
  opacity:0;
  transform:translateY(10px);
  animation:fadeUp 0.8s forwards;
}
@keyframes fadeUp{to{opacity:1;transform:translateY(0);}}

/* buttons */
.btn{
  padding:12px 20px;
  border:none;
  border-radius:30px;
  font-size:20px;
  cursor:pointer;
  margin:10px;
}

.red{background:#ff4d6d;color:white;}
.white{background:white;color:#333;}

#result{margin-top:20px;line-height:1.6;}
#hidden{margin-top:15px;opacity:0;transition:0.5s;}

/* floating hearts */
.float-heart{
  position:fixed;
  bottom:-20px;
  font-size:16px;
  animation:rise 6s linear forwards;
}
@keyframes rise{to{transform:translateY(-110vh);}}

/* explosion */
.heart{
  position:fixed;
  font-size:18px;
  animation:explode 0.8s ease forwards;
}
@keyframes explode{
  to{opacity:0;transform:translate(var(--x),var(--y));}
}
</style>
</head>

<body>

<div id="intro">
  For Veda 🌸<br><small>wait a second...</small>
</div>

<div class="card">

<h1>For You 🌸</h1>

<div id="text"></div>

<div style="margin-top:20px;">
  <p><b>If this made you feel a little special…</b></p>
  <p>tap ❤️… otherwise 🤍</p>

  <button class="btn red" onclick="yesClick(event)">❤️</button>
  <button class="btn white" id="whiteBtn" onclick="noClick()">🤍</button>
</div>

<div id="result"></div>
<div id="hidden"></div>

</div>

<script>

// SAME TEXT AS BEFORE (UNCHANGED)
setTimeout(showText,2800);

const lines=[
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
  let c=document.getElementById("text");
  lines.forEach((l,i)=>{
    let p=document.createElement("p");
    p.className="line";
    p.style.animationDelay=(i*0.5)+"s";
    p.innerHTML=l;
    c.appendChild(p);
  });
}

// floating hearts (optimized)
setInterval(()=>{
  if(document.querySelectorAll(".float-heart").length>8) return;
  let h=document.createElement("div");
  h.className="float-heart";
  h.innerHTML="❤️";
  h.style.left=Math.random()*100+"vw";
  document.body.appendChild(h);
  setTimeout(()=>h.remove(),6000);
},1800);

// white → red (emotional trick)
setTimeout(()=>{
  let w=document.getElementById("whiteBtn");
  w.innerHTML="❤️";
  w.classList.remove("white");
  w.classList.add("red");
},6000);

// YES
function yesClick(e){
  document.getElementById("result").innerHTML=
  "That’s all I wanted 💖<br><br>...and yeah, I meant what I said that day.";

  explode(e);

  setTimeout(()=>{
    let h=document.getElementById("hidden");
    h.style.opacity=1;
    typeWriter("...you probably felt it too 😌",h);
  },2000);
}

// NO (tease)
function noClick(){
  document.getElementById("result").innerHTML=
  "Hmm 🤍<br><br>or maybe you just don’t admit things easily 😏";
}

// explosion
function explode(e){
  for(let i=0;i<10;i++){
    let heart=document.createElement("div");
    heart.className="heart";
    heart.innerHTML="❤️";

    heart.style.setProperty('--x',(Math.random()-0.5)*150+"px");
    heart.style.setProperty('--y',(Math.random()-0.5)*150+"px");

    heart.style.left=e.clientX+"px";
    heart.style.top=e.clientY+"px";

    document.body.appendChild(heart);
    setTimeout(()=>heart.remove(),800);
  }
}

// typing effect
function typeWriter(text,el,i=0){
  if(i<text.length){
    el.innerHTML+=text.charAt(i);
    setTimeout(()=>typeWriter(text,el,i+1),40);
  }
}

</script>

</body>
</html>
