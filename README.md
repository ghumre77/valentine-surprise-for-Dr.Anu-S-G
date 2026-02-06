<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>For My Love ❤️</title>
<script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;700&display=swap" rel="stylesheet">

<style>
body{
margin:0;
font-family:'Poppins',sans-serif;
overflow:hidden;
background: linear-gradient(135deg,#ff9ecf,#ffcce6);
display:flex;
justify-content:center;
align-items:center;
height:100vh;
text-align:center;
}

/* floating hearts */
.heart{
position:fixed;
color:rgba(255,0,100,0.3);
animation: float 6s linear infinite;
font-size:20px;
}
@keyframes float{
0%{transform:translateY(100vh);opacity:1;}
100%{transform:translateY(-10vh);opacity:0;}
}

.container{
background:white;
padding:30px;
border-radius:20px;
box-shadow:0 10px 40px rgba(0,0,0,0.15);
max-width:350px;
width:90%;
}

h1{
color:#e60073;
font-size:22px;
}

button{
padding:12px 25px;
margin:10px;
border:none;
border-radius:30px;
font-size:16px;
cursor:pointer;
transition:0.3s;
}

#yes{
background:#ff4da6;
color:white;
}

#no{
background:#eee;
position:absolute;
}

.finalPage{
position:fixed;
top:0;
left:0;
width:100%;
height:100%;
background:linear-gradient(135deg,#ff9ecf,#ffcce6);
display:none;
flex-direction:column;
justify-content:center;
align-items:center;
color:white;
text-align:center;
padding:20px;
}

.slideshow{
width:90%;
max-width:300px;
border-radius:20px;
box-shadow:0 10px 30px rgba(0,0,0,0.3);
margin-bottom:20px;
}

.finalPage h2{
font-size:24px;
}

.finalPage p{
font-size:16px;
}
</style>
</head>

<body>

<div class="container" id="mainBox">
<h1>❤️ Anushka ❤️<br>Will you be my Valentine? 💖</h1>
<button id="yes">Yes 💕</button>
<button id="no">No 😜</button>
</div>

<div class="finalPage" id="finalPage">
<img id="slide" class="slideshow" src="">
<h2>Happy Valentine’s Bayko Day ❤️</h2>
<p>Every moment with you feels like my favorite dream come true ✨💖</p>
</div>

<script>

/* floating hearts */
for(let i=0;i<20;i++){
let heart=document.createElement("div");
heart.className="heart";
heart.innerHTML="❤";
heart.style.left=Math.random()*100+"vw";
heart.style.fontSize=(15+Math.random()*25)+"px";
heart.style.animationDuration=(4+Math.random()*4)+"s";
document.body.appendChild(heart);
}

/* No button run away */
let noBtn=document.getElementById("no");
noBtn.addEventListener("mouseover",()=>{
noBtn.style.top=Math.random()*80+"%";
noBtn.style.left=Math.random()*80+"%";
});

/* Yes click */
document.getElementById("yes").addEventListener("click",()=>{
confetti({particleCount:200,spread:100});
setTimeout(()=>{
document.getElementById("mainBox").style.display="none";
document.getElementById("finalPage").style.display="flex";
startSlide();
},2000);
});

/* slideshow images (your photos added) */
let images=[
"82571.jpg",
"82364.jpg",
"82280.jpg"
];

let index=0;
function startSlide(){
document.getElementById("slide").src=images[0];
setInterval(()=>{
index=(index+1)%images.length;
document.getElementById("slide").src=images[index];
},2500);
}

</script>

</body>
</html>
