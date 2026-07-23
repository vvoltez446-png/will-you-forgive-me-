Loading...

❤️

"I have something to tell you."

        [ Open ]

⬇️ click

📩 Envelope opens...

⬇️

💌 Letter slowly appears...

⬇️

Typing...

"I'm truly sorry..."

⬇️

🌹

Will You Forgive Me?

[ Yes ❤️ ]   [ I Need More Time ]<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Will You Forgive Me?</title>

<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;500;700&display=swap" rel="stylesheet">

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:'Poppins',sans-serif;
}

body{
    overflow:hidden;
    background:linear-gradient(135deg,#0f172a,#1e293b,#111827);
    height:100vh;
    display:flex;
    justify-content:center;
    align-items:center;
    color:white;
}

.card{
    width:90%;
    max-width:700px;
    background:rgba(255,255,255,.08);
    backdrop-filter:blur(18px);
    border:1px solid rgba(255,255,255,.15);
    border-radius:25px;
    padding:45px;
    text-align:center;
    box-shadow:0 15px 40px rgba(0,0,0,.4);
    animation:fade 1.5s;
    z-index:10;
}

h1{
    font-size:42px;
    margin-bottom:10px;
}

.type{
    color:#ff8fab;
    font-size:18px;
    height:28px;
    margin-bottom:25px;
}

p{
    line-height:1.8;
    font-size:17px;
    color:#f1f1f1;
}

.buttons{
    margin-top:35px;
}

button{
    padding:14px 35px;
    margin:10px;
    border:none;
    border-radius:50px;
    font-size:16px;
    cursor:pointer;
    transition:.3s;
}

.yes{
    background:#ff4d6d;
    color:white;
}

.yes:hover{
    transform:scale(1.08);
}

.time{
    background:transparent;
    border:2px solid white;
    color:white;
}

.time:hover{
    background:white;
    color:black;
}

#message{
    margin-top:25px;
    color:#ffd6e0;
    font-size:18px;
    font-weight:500;
}

.heart{
    position:absolute;
    color:#ff4d6d;
    animation:float 10s linear infinite;
    opacity:.5;
}

@keyframes float{
from{
transform:translateY(100vh) scale(.5);
}
to{
transform:translateY(-120vh) scale(1.5);
}
}

@keyframes fade{
from{
opacity:0;
transform:translateY(30px);
}
to{
opacity:1;
transform:translateY(0);
}
}

canvas{
position:absolute;
top:0;
left:0;
pointer-events:none;
}
</style>

</head>
<body>

<canvas id="canvas"></canvas>

<div class="card">

<h1>Will You Forgive Me?</h1>

<div class="type" id="typing"></div>

<p>
I'm truly sorry for hurting you.
<br><br>
I know that saying <b>"I'm sorry"</b> isn't enough to erase the pain I caused, and I understand if your heart needs time.
<br><br>
If I could go back and undo my mistakes, I would without hesitation. But since I can't, all I can do is be honest, take responsibility, and work every day to become someone who deserves your trust again.
<br><br>
You mean so much to me, and I never want my mistakes to define what we have.
<br><br>
Whether your answer comes today or another day, I'll respect it.
</p>

<div class="buttons">
<button class="yes" onclick="forgive()">Yes ❤️</button>
<button class="time" onclick="timeNeed()">I Need More Time</button>
</div>

<div id="message"></div>

</div>

<script>

const words=[
"I miss your smile.",
"I miss us.",
"I'll keep choosing you.",
"I'll become better.",
"You are worth every effort."
];

let i=0,j=0,erase=false;

function type(){

const text=document.getElementById("typing");

if(!erase){
text.innerHTML=words[i].substring(0,j++);
if(j>words[i].length){
erase=true;
setTimeout(type,1500);
return;
}
}
else{
text.innerHTML=words[i].substring(0,j--);
if(j<0){
erase=false;
i=(i+1)%words.length;
}
}

setTimeout(type,erase?40:90);

}

type();

function forgive(){

document.getElementById("message").innerHTML=
"Thank you... ❤️ I'll spend every day proving that your forgiveness wasn't wasted.";

confetti();

}

function timeNeed(){

document.getElementById("message").innerHTML=
"I understand. I'll wait patiently, respect your space, and continue showing you through my actions.";

}

for(let i=0;i<35;i++){

const heart=document.createElement("div");

heart.className="heart";

heart.innerHTML="❤";

heart.style.left=Math.random()*100+"vw";

heart.style.fontSize=(15+Math.random()*25)+"px";

heart.style.animationDuration=(6+Math.random()*6)+"s";

heart.style.animationDelay=Math.random()*6+"s";

document.body.appendChild(heart);

}

const canvas=document.getElementById("canvas");
const ctx=canvas.getContext("2d");

canvas.width=innerWidth;
canvas.height=innerHeight;

let particles=[];

function confetti(){

for(let i=0;i<180;i++){

particles.push({

x:innerWidth/2,

y:150,

dx:(Math.random()-.5)*10,

dy:Math.random()*-10,

size:Math.random()*6+3,

life:120

});

}

}

function animate(){

ctx.clearRect(0,0,canvas.width,canvas.height);

particles.forEach((p,index)=>{

ctx.fillStyle=`hsl(${Math.random()*360},100%,60%)`;

ctx.fillRect(p.x,p.y,p.size,p.size);

p.x+=p.dx;

p.y+=p.dy;

p.dy+=0.15;

p.life--;

if(p.life<=0)particles.splice(index,1);

});

requestAnimationFrame(animate);

}

animate();

</script>

</body>
</html>
