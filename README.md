<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>For You 🌸</title>

<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600&display=swap" rel="stylesheet">

<style>
*{margin:0;padding:0;box-sizing:border-box;}

body{
  min-height:100vh;
  font-family:'Poppins',sans-serif;
  display:flex;
  justify-content:center;
  align-items:center;
  padding:20px;

  background:linear-gradient(135deg,#5f6dfc,#7c3aed);
  color:#fff;
}

/* intro */
#intro{
  position:fixed;
  inset:0;
  display:flex;
  justify-content:center;
  align-items:center;
  font-size:1.8rem;
  background:rgba(0,0,0,0.4);
  backdrop-filter:blur(10px);
  z-index:10;
  animation:fadeOut 2.5s forwards;
  animation-delay:2s;
}
@keyframes fadeOut{to{opacity:0;visibility:hidden;}}

/* card */
.card{
  width:100%;
  max-width:650px;
  max-height:85vh;
  overflow-y:auto;

  padding:45px 40px;

  background:rgba(255,255,255,0.1);
  backdrop-filter:blur(18px);

  border-radius:24px;
  border:1px solid rgba(255,255,255,0.15);

  box-shadow:0 20px 50px rgba(0,0,0,0.25);
  text-align:center;
}

/* heading */
h1{
  margin-bottom:25px;
  font-weight:500;
}

/* text animation */
.line{
  opacity:0;
  transform:translateY(15px);
  animation:fadeUp 0.7s forwards;
}
@keyframes fadeUp{
  to{opacity:1;transform:translateY(0);}
}

/* buttons */
.btn{
  padding:12px 24px;
  border-radius:30px;
  font-size:18px;
  border:none;
  cursor:pointer;
  margin:10px;
  transition:0.25s;
}

.red{
  background:#ff4d6d;
  color:white;
}
.red:hover{transform:scale(1.05);}

.white{
  background:white;
  color:#333;
}
.white:hover{transform:scale(1.05);}

/* result */
#result{margin-top:20px;line-height:1.6;}
#hidden{margin-top:12px;opacity:0;transition:0.5s;}
</style>
</head>

<body>

<div id="intro">
  For Veda 🌸
</div>

<div class="card">

<h1>For You 🌸</h1>

<div id="text"></div>

<div style="margin-top:25px;">
  <p><b>If this made you feel a little special…</b></p>
  <p>tap ❤️… otherwise 🤍</p>

  <button class="btn red" onclick="yesClick()">❤️</button>
  <button class="btn white" onclick="noClick()">🤍</button>
</div>

<div id="result"></div>
<div id="hidden"></div>

</div>

<script>

// TEXT (UNCHANGED)
setTimeout(showText,2200);

const lines=[
"Good morning Veda ❤️",

"I don’t really know why… but I felt like writing this.",

"You’re actually a really good human being.",
"The way you think… it’s rare.",
"And honestly… not everyone has that.",

"There’s something about your vibe,",
"it’s a little different… in a way I can’t really explain,",
"but it makes you stand out without trying.",

"Not gonna lie… talking to you feels different.",
"In a way I didn’t expect… but I don’t mind it.",

"And maybe that’s what makes it interesting.",

"And… don’t overthink things too much,",
"not everything really deserves that space in your mind.",

"✨ Keep smiling ✨",
"it actually changes the vibe around you more than you think.",

"So yeah… just stay the way you are."
];

function showText(){
  let c=document.getElementById("text");
  lines.forEach((l,i)=>{
    setTimeout(()=>{
      let p=document.createElement("p");
      p.className="line";
      p.innerHTML=l;
      c.appendChild(p);
    }, i*700);
  });
}

// YES
function yesClick(){
  document.getElementById("result").innerHTML=
  "That’s all I wanted 💖<br><br>...and yeah, I meant what I said that day.";

  setTimeout(()=>{
    let h=document.getElementById("hidden");
    h.style.opacity=1;
    typeWriter("...you probably felt it too 😌",h);
  },1200);
}

// NO
function noClick(){
  document.getElementById("result").innerHTML=
  "Hmm okay 🤍<br><br>maybe it wasn't that special...<br>but I still meant what I said 🙂";
}

// typing effect
function typeWriter(text,el,i=0){
  if(i<text.length){
    el.innerHTML+=text.charAt(i);
    setTimeout(()=>typeWriter(text,el,i+1),35);
  }
}

</script>

</body>
</html>
