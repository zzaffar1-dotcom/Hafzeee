<!DOCTYPE html>
<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>For Hafsa ❤️</title>

<style>
body{
margin:0;
font-family:system-ui;
background:black;
color:white;
overflow:hidden;
text-align:center;
}

/* STARS */
.stars{
position:fixed;
width:100%;
height:100%;
background:url("https://www.transparenttextures.com/patterns/stardust.png");
animation:moveStars 120s linear infinite;
z-index:-1;
}
@keyframes moveStars{
from{background-position:0 0}
to{background-position:10000px 5000px}
}

/* SCREEN SECTIONS */
.section{
display:none;
padding:20px;
min-height:100vh;
}

/* INTRO */
#intro{
display:flex;
flex-direction:column;
justify-content:center;
align-items:center;
height:100vh;
}

button{
padding:14px 32px;
font-size:1.2rem;
border:none;
border-radius:40px;
margin:10px;
background:#ff2e63;
color:white;
}

/* SLIDESHOW */
.slideshow{
width:90vw;
max-width:350px;
height:420px;
margin:auto;
border-radius:20px;
overflow:hidden;
position:relative;
}
.slide{
position:absolute;
width:100%;
height:100%;
object-fit:cover;
opacity:0;
transition:opacity 2s;
}
.slide.active{opacity:1}

/* LETTER */
.card{
background:white;
color:#333;
padding:25px;
border-radius:15px;
max-width:320px;
margin:20px auto;
}

/* HEARTS */
.heart{
position:absolute;
font-size:22px;
animation:float 6s linear infinite;
}
@keyframes float{
0%{transform:translateY(100vh);opacity:0}
50%{opacity:1}
100%{transform:translateY(-10vh);opacity:0}
}

/* RING */
#ring{
font-size:5rem;
animation:pulse 1.5s infinite;
cursor:pointer;
}
@keyframes pulse{
0%{transform:scale(1)}
50%{transform:scale(1.2)}
100%{transform:scale(1)}
}

/* FINAL */
#final{
font-size:2.5rem;
}

/* CONFETTI */
.confetti{
position:absolute;
width:8px;
height:8px;
animation:fall 3s linear forwards;
}
@keyframes fall{
to{transform:translateY(100vh) rotate(720deg);opacity:0}
}
</style>
</head>

<body>

<div class="stars"></div>

<audio id="music" loop>
<source src="https://cdn.pixabay.com/download/audio/2022/03/15/audio_115b9b9c9a.mp3">
</audio>

<audio id="voice">
<source src="voice.mp3">
</audio>

<!-- INTRO -->
<div id="intro" class="section" style="display:flex">
<h1>Our Love Story ❤️</h1>
<button onclick="start()">Begin Journey</button>
</div>

<!-- MEMORIES -->
<div id="memories" class="section">
<h1>Our Beautiful Memories ✨</h1>
<div class="slideshow">
<img src="photo1.jpg" class="slide active">
<img src="photo2.jpg" class="slide">
<img src="photo3.jpg" class="slide">
<img src="photo4.jpg" class="slide">
<img src="photo5.jpg" class="slide">
</div>
<button onclick="next('letter')">Continue</button>
</div>

<!-- LOVE LETTER -->
<div id="letter" class="section">
<div class="card">
Hafsa…  
You are my peace, my happiness, my destiny.  
Every moment with you feels like magic.  
Every heartbeat whispers your name.  

I don’t just love you…  
I choose you… always ❤️
</div>
<button onclick="next('heartTest')">One More Thing…</button>
</div>

<!-- HEART TEST -->
<div id="heartTest" class="section">
<h2>Press the button if your heart beats for me ❤️</h2>
<button onclick="next('proposal')">My Heart Beats For You</button>
</div>

<!-- PROPOSAL -->
<div id="proposal" class="section">
<h1>Hafsa… Will You Be Mine Forever?</h1>
<div id="ring" onclick="next('final');fireworks()">💍</div>
<p>Tap the ring…</p>
</div>

<!-- FINAL -->
<div id="final" class="section">
She Said YES ❤️💍  
<br><br>
Forever Begins Now 🌹
</div>

<script>

function start(){
intro.style.display="none";
memories.style.display="block";
music.play();
voice.play();
}

function next(id){
document.querySelectorAll(".section").forEach(s=>s.style.display="none");
document.getElementById(id).style.display="block";
}

/* SLIDESHOW */
let slides=document.querySelectorAll(".slide");
let i=0;
setInterval(()=>{
slides[i].classList.remove("active");
i=(i+1)%slides.length;
slides[i].classList.add("active");
},3000);

/* HEARTS */
setInterval(()=>{
let h=document.createElement("div");
h.className="heart";
h.innerHTML="❤";
h.style.left=Math.random()*100+"vw";
document.body.appendChild(h);
setTimeout(()=>h.remove(),6000);
},300);

/* FIREWORKS */
function fireworks(){
for(let i=0;i<400;i++){
let c=document.createElement("div");
c.className="confetti";
c.style.left=Math.random()*100+"vw";
c.style.background=`hsl(${Math.random()*360},100%,70%)`;
document.body.appendChild(c);
}
}
</script>

</body>
</html>
