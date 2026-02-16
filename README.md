<!DOCTYPE html>
<html lang="pt">
<head>
<meta charset="UTF-8">
<title>2 Meses ❤️</title>
<style>
body{
margin:0;
font-family:'Segoe UI', sans-serif;
background:linear-gradient(135deg,#3b0000,#8b0000,#1a0000);
color:white;
text-align:center;
overflow:hidden;
}

/* ESTRELAS */
.stars{
position:fixed;
width:100%;
height:100%;
}
.star{
position:absolute;
width:2px;
height:2px;
background:white;
opacity:0.6;
animation: twinkle 2s infinite alternate;
}
@keyframes twinkle{
from{opacity:0.2;}
to{opacity:1;}
}

/* CORAÇÕES BRANCOS A CAIR */
.falling-heart{
position:fixed;
top:-10px;
color:white;
font-size:20px;
animation: fall linear forwards;
}
@keyframes fall{
to{
transform:translateY(100vh);
opacity:0;
}
}

/* ECRÃ INICIAL */
#inicio{
height:100vh;
display:flex;
justify-content:center;
align-items:center;
flex-direction:column;
padding:0 20px; /* evita corte do coração */
}

/* Coração SVG */
#heartContainer{
width:180px;
height:180px;
cursor:pointer;
position:relative;
margin-bottom:20px;
}

svg{
width:100%;
height:100%;
}

#heartOutline{
fill:none;
stroke:white;
stroke-width:2; /* borda mais fina */
}

#heartFill{
fill:white;
stroke:none;
clip-path:url(#clip);
}

/* CONTEÚDO */
#conteudo{
display:none;
}

/* ENVELOPE */
.envelope{
width:320px;
max-width:90vw;
height:220px;
background:#5c0000;
margin:80px auto;
position:relative;
cursor:pointer;
border-radius:15px;
box-shadow:0 0 25px rgba(255,0,0,0.6);
transition:opacity 0.5s;
}

.flap{
position:absolute;
width:100%;
height:100%;
background:#7a0000;
clip-path: polygon(0 0, 100% 0, 50% 50%);
transition:0.8s;
}

.open .flap{
transform:rotateX(180deg);
transform-origin:top;
}

.carta{
display:none;
padding:30px;
width:85%;
margin:20px auto;
background:rgba(255,255,255,0.08);
border-radius:15px;
backdrop-filter:blur(10px);
}

img{
width:180px;
border-radius:12px;
margin:10px;
}

button{
padding:10px 20px;
border:none;
border-radius:8px;
background:white;
color:#8b0000;
cursor:pointer;
font-weight:bold;
margin-top:20px;
}

/* CONTADOR */
#contador{
margin-top:20px;
font-size:18px;
font-weight:bold;
}
</style>
</head>

<body>

<div class="stars" id="stars"></div>

<div id="inicio">
<div id="heartContainer">
<svg viewBox="0 0 32 29.6">
<defs>
<clipPath id="clip">
<rect id="clipRect" x="0" y="29.6" width="32" height="0"></rect>
</clipPath>
</defs>
<path id="heartFill" d="M23.6,0c-2.9,0-5.4,1.6-6.6,4C15.8,1.6,13.3,0,10.4,0
C4.6,0,0,4.6,0,10.4c0,7.3,8.2,12.9,16,19.2c7.8-6.3,16-11.9,16-19.2C32,4.6,27.4,0,23.6,0z"/>
<path id="heartOutline" d="M23.6,0c-2.9,0-5.4,1.6-6.6,4C15.8,1.6,13.3,0,10.4,0
C4.6,0,0,4.6,0,10.4c0,7.3,8.2,12.9,16,19.2c7.8-6.3,16-11.9,16-19.2C32,4.6,27.4,0,23.6,0z"/>
</svg>
</div>
<p>Clica no coração até encher xuxu</p>
</div>

<div id="conteudo">
<div class="envelope" id="envelope" onclick="abrirCarta(this)">
<div class="flap"></div>
</div>

<div class="carta" id="carta">
<h1>Feliz 2 Meses ❤️</h1>
<p>
Dois meses podem parecer pouco tempo para o mundo,
mas para mim foram suficientes para perceber
que foste das melhores coisas que me aconteceu.<br><br>

Obrigada por me fazeres rir,
por estares lá quando preciso,
e por transformares dias normais
em momentos que eu quero guardar para sempre.<br><br>

Desde <b>17/12/2025</b> que a minha vida ficou mais divertida.
Gosto de estar ao teu lado.
amo te imenso meu amor ❤️
</p>

<div>
<img src="https://mail.google.com/mail/u/0?ui=2&ik=d7cd61d4df&attid=0.1&permmsgid=msg-a:r-86899864564591495&th=19c63349fcfdb905&view=fimg&fur=ip&permmsgid=msg-a:r-86899864564591495&sz=s0-l75-ft&attbid=ANGjdJ9hewxEO2Bzp5t8UesV_UnZ59U8yB-UqilQ2NrjToimSQh51IRwZbz-B4ygkLHvozlf_DNMREJu8NLrPWg_83Ftjes9YmKqxkEZxx7gWJ9_B5repBsksuwX3sM&disp=emb&realattid=ii_19c633428de74196fae1&zw">
<img src="https://mail.google.com/mail/u/0?ui=2&ik=d7cd61d4df&attid=0.2&permmsgid=msg-a:r-86899864564591495&th=19c63349fcfdb905&view=fimg&fur=ip&permmsgid=msg-a:r-86899864564591495&sz=s0-l75-ft&attbid=ANGjdJ9_cxBMIzxWPJlIab2P23dmvF8GQXdd0zOj3ozlq_saDJqKhFCYWL71PrJJt4usyRBrP1DRO_Sp9fj9CSTEMq04cP6gcWpeXFPVwgEtYstY5GujUpx1As6sZd8&disp=emb&realattid=ii_19c63347cdec2bd191a2&zw">
</div>

<div id="contador"></div>
</div>
</div>

<script>
/* ESTRELAS */
for(let i=0;i<80;i++){
let star=document.createElement("div");
star.className="star";
star.style.top=Math.random()*100+"%";
star.style.left=Math.random()*100+"%";
star.style.animationDuration=(Math.random()*3+1)+"s";
document.getElementById("stars").appendChild(star);
}

/* CORAÇÕES A CAIR */
function fallingHearts(){
let heart=document.createElement("div");
heart.className="falling-heart";
heart.innerHTML="🤍";
heart.style.left=Math.random()*100+"vw";
heart.style.animationDuration=(Math.random()*3+2)+"s";
document.body.appendChild(heart);
setTimeout(()=>heart.remove(),5000);
}
setInterval(fallingHearts,400);

/* EXPLOSÃO */
function explosion(){
for(let i=0;i<80;i++){
let heart=document.createElement("div");
heart.innerHTML="🤍";
heart.style.position="fixed";
heart.style.left="50%";
heart.style.top="50%";
heart.style.fontSize="20px";
heart.style.pointerEvents="none";

let angle=Math.random()*2*Math.PI;
let distance=Math.random()*300+50;

let x=Math.cos(angle)*distance;
let y=Math.sin(angle)*distance;

heart.style.transition="1s ease-out";
document.body.appendChild(heart);

setTimeout(()=>{
heart.style.transform=`translate(${x}px, ${y}px)`;
heart.style.opacity="0";
},10);

setTimeout(()=>{
heart.remove();
},1000);
}
}

/* CORAÇÃO REAL QUE ENCHE */
let clicks = 0;
const maxClicks = 10;
const clipRect = document.getElementById("clipRect");

document.getElementById("heartContainer").addEventListener("click", ()=>{
clicks++;
let height = 29.6 * (clicks / maxClicks);
clipRect.setAttribute("y", 29.6 - height);
clipRect.setAttribute("height", height);

if(clicks >= maxClicks){
explosion();
setTimeout(()=>{
document.getElementById("inicio").style.display="none";
document.getElementById("conteudo").style.display="block";
startCounter();
},1200);
}
});

/* ABRIR CARTA */
function abrirCarta(element){
element.classList.add("open");
element.style.opacity = "0";
setTimeout(()=> element.style.display = "none", 500);
document.getElementById("carta").style.display="block";
}

/* CONTADOR DINÂMICO */
function startCounter(){
const startDate = new Date("2025-12-17");

function updateCounter(){
const now = new Date();
let diff = now - startDate;

const days = Math.floor(diff / (1000*60*60*24));
diff -= days * (1000*60*60*24);

const hours = Math.floor(diff / (1000*60*60));
diff -= hours * (1000*60*60);

const minutes = Math.floor(diff / (1000*60));
diff -= minutes * (1000*60);

const seconds = Math.floor(diff / 1000);

document.getElementById("contador").innerHTML=
`Já passaram ${days} dias, ${hours}h ${minutes}m ${seconds}s ❤️`;
}

updateCounter();
setInterval(updateCounter,1000);
}
</script>

</body>
</html>
