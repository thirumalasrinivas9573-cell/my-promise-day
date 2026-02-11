<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>My Royal Princess 💖</title>

<link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@600&family=Dancing+Script:wght@700&display=swap" rel="stylesheet">

<style>
body{
    margin:0;
    padding:0;
    height:100vh;
    display:flex;
    justify-content:center;
    align-items:center;
    background: radial-gradient(circle at top, #4a0e6f, #ff4da6, #000);
    font-family:'Cinzel', serif;
    overflow:hidden;
    color:white;
}

.container{
    width:360px;
    height:640px;
    border-radius:25px;
    background:rgba(255,255,255,0.08);
    backdrop-filter:blur(15px);
    box-shadow:0 0 40px pink;
    padding:25px;
    text-align:center;
    position:relative;
}

.slide{display:none;animation:fade 1s;}
.active{display:block;}

h1{
    color:gold;
    text-shadow:0 0 20px gold;
    font-size:22px;
}

p{
    font-family:'Dancing Script', cursive;
    font-size:20px;
    line-height:1.6;
    text-shadow:0 0 10px pink;
}

button{
    margin-top:20px;
    padding:10px 25px;
    border:none;
    border-radius:30px;
    background:linear-gradient(45deg,pink,gold);
    font-weight:bold;
    cursor:pointer;
    box-shadow:0 0 20px pink;
    transition:0.3s;
}
button:hover{
    transform:scale(1.1);
}

@keyframes fade{
    from{opacity:0;}
    to{opacity:1;}
}

/* Floating Hearts */
.heart{
    position:absolute;
    color:#ff99cc;
    animation:float 6s linear infinite;
}
@keyframes float{
    0%{transform:translateY(100%);opacity:1;}
    100%{transform:translateY(-100%);opacity:0;}
}

/* Fireworks */
.firework{
    position:absolute;
    width:6px;height:6px;
    background:pink;
    border-radius:50%;
    animation:explode 1.5s ease-out;
}
@keyframes explode{
    0%{transform:scale(1);}
    100%{transform:scale(25);opacity:0;}
}
</style>
</head>

<body>

<div class="container">

<div class="slide active">
<h1>👑 Happy Promise Day 👑</h1>
<p id="typeText"></p>
<button onclick="next()">Enter My Heart 💖</button>
</div>

<div class="slide">
<h1>🌹 My Destiny</h1>
<p>
Like Radhe & Shyam…  
Our love feels written by destiny.  
In every lifetime,  
I will search only for you, my Princess.
</p>
<button onclick="next()">Next 💞</button>
</div>

<div class="slide">
<h1>💫 My Promise</h1>
<p>
I promise to protect your smile,  
respect your dreams,  
hold your hand in every storm,  
and love you more each day.
</p>
<button onclick="next()">Next 💞</button>
</div>

<div class="slide">
<h1>💓 Pure Love</h1>
<p>
Love is not just words…  
It is feeling your presence  
even in silence.  
You are my peace and my heartbeat.
</p>
<button onclick="next()">Next 💞</button>
</div>

<div class="slide">
<h1>🌸 My Princess</h1>
<p>
You are not my Queen…  
You are my beautiful Princess  
with the softest heart  
and the brightest smile.
</p>
<button onclick="next()">Next 💞</button>
</div>

<div class="slide">
<h1>💍 Forever With Me?</h1>
<p>
Will you be my Princess forever,  
walk beside me,  
and make our love story legendary?
</p>
<button onclick="celebrate()">YES 💖</button>
<button id="noBtn" onmouseover="moveNo()">NO 🙈</button>
</div>

<div class="slide">
<h1>🎆 Celebration of Love 🎆</h1>
<p>
Now every sunrise belongs to us,  
every night shines brighter,  
because my Princess said YES 💞
</p>
<button onclick="next()">Next</button>
</div>

<div class="slide">
<h1>❤️ Forever Promise ❤️</h1>
<p>
Yesterday I liked you…  
Today I love you…  
Tomorrow I will love you more.  
Forever yours, my Princess.
</p>
</div>

</div>

<script>
let slides=document.querySelectorAll(".slide");
let current=0;

function next(){
slides[current].classList.remove("active");
current++;
slides[current].classList.add("active");
}

function celebrate(){
for(let i=0;i<25;i++){
let fire=document.createElement("div");
fire.className="firework";
fire.style.top=Math.random()*100+"%";
fire.style.left=Math.random()*100+"%";
document.body.appendChild(fire);
setTimeout(()=>fire.remove(),1500);
}
next();
}

function moveNo(){
let btn=document.getElementById("noBtn");
btn.style.position="absolute";
btn.style.left=Math.random()*250+"px";
btn.style.top=Math.random()*450+"px";
}

setInterval(()=>{
let heart=document.createElement("div");
heart.className="heart";
heart.innerHTML="💖";
heart.style.left=Math.random()*100+"%";
heart.style.bottom="0";
heart.style.fontSize=(18+Math.random()*20)+"px";
document.body.appendChild(heart);
setTimeout(()=>heart.remove(),6000);
},800);

/* Typewriter Romantic Intro */
let text="Today, I promise not just love... but loyalty, respect, protection and forever happiness. You are my heart, my dream, my Royal Princess.";
let i=0;
function typeWriter(){
if(i<text.length){
document.getElementById("typeText").innerHTML+=text.charAt(i);
i++;
setTimeout(typeWriter,40);
}}
typeWriter();
</script>

</body>
</html>
