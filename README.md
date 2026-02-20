import webbrowser
from pathlib import Path

html_content = """
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Special Surprise for Jyoshtna Sri 💖</title>

<link href="https://fonts.googleapis.com/css2?family=Great+Vibes&family=Poppins:wght@300;500;700&display=swap" rel="stylesheet">
<script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>

<style>
body {
  margin: 0;
  overflow: hidden;
  font-family: 'Poppins', sans-serif;
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  background: linear-gradient(-45deg,#ff9a9e,#fad0c4,#fbc2eb,#a6c1ee);
  background-size: 400% 400%;
  animation: gradientBG 15s ease infinite;
}

@keyframes gradientBG {
  0%{background-position:0% 50%;}
  50%{background-position:100% 50%;}
  100%{background-position:0% 50%;}
}

/* Floating Hearts */
.heart {
  position:absolute;
  color:rgba(255,255,255,0.5);
  animation: float 10s linear infinite;
}
@keyframes float {
  from{transform:translateY(100vh);}
  to{transform:translateY(-10vh);}
}

/* Glass Card */
.container {
  text-align:center;
  width:420px;
  padding:50px 40px;
  border-radius:30px;
  background:rgba(255,255,255,0.2);
  backdrop-filter:blur(15px);
  box-shadow:0 25px 60px rgba(0,0,0,0.2);
  transition:opacity 1s ease;
}

.container.hide { opacity:0; }

.slide { display:none; }
.slide.active { display:block; animation:fadeIn 1s ease; }

@keyframes fadeIn {
  from{opacity:0; transform:translateY(20px);}
  to{opacity:1; transform:translateY(0);}
}

h1 {
  font-family:'Great Vibes', cursive;
  font-size:3.5rem;
  color:#fff;
  text-shadow:0 0 25px #ff69b4;
  animation: glow 2s infinite alternate;
}

@keyframes glow {
  from{text-shadow:0 0 15px #ff69b4;}
  to{text-shadow:0 0 35px #ff1493;}
}

p {
  color:#fff;
  font-size:1.1rem;
}

button {
  margin-top:25px;
  padding:12px 35px;
  border-radius:40px;
  border:none;
  font-weight:bold;
  cursor:pointer;
  background:linear-gradient(45deg,#ff4d6d,#ff99cc);
  color:white;
  transition:0.3s;
}
button:hover { transform:scale(1.1); }

/* Final Name */
#namePop {
  position:fixed;
  top:50%;
  left:50%;
  transform:translate(-50%,-50%) scale(0);
  font-family:'Great Vibes', cursive;
  font-size:6rem;
  color:#ff1493;
  text-shadow:0 0 40px #ff69b4;
  z-index:1;
  transition:transform 1.2s cubic-bezier(.68,-0.55,.27,1.55);
}
#namePop.show { transform:translate(-50%,-50%) scale(1); }

/* Teddy */
#teddy {
  position:fixed;
  bottom:40px;
  left:-200px;
  font-size:120px;
  z-index:3;
}
#teddy.show {
  animation:walkIn 2s forwards, bounce 2s infinite 2s;
}

@keyframes walkIn {
  to{ left:50%; transform:translateX(-50%); }
}
@keyframes bounce {
  0%,100%{ transform:translateX(-50%) translateY(0);}
  50%{ transform:translateX(-50%) translateY(-15px);}
}

/* Balloons */
.balloon {
  position:absolute;
  font-size:40px;
  animation:floatBalloon 5s ease-in-out infinite;
}
@keyframes floatBalloon {
  0%,100%{transform:translateY(0);}
  50%{transform:translateY(-30px);}
}
</style>
</head>

<body>

<div class="container" id="mainContainer">

<div class="slide active" id="slide1">
  <h1>Jyoshtna Sri 💖</h1>
  <p>I made something special just for you...</p>
  <button onclick="nextSlide()">Start ✨</button>
</div>

<div class="slide" id="slide2">
  <h1>Your Smile 😊</h1>
  <p>Your smile can brighten the darkest days.</p>
  <button onclick="nextSlide()">Next 💕</button>
</div>

<div class="slide" id="slide3">
  <h1>Your Eyes ✨</h1>
  <p>Your eyes shine brighter than the stars.</p>
  <button onclick="nextSlide()">More 💖</button>
</div>

<div class="slide" id="slide4">
  <h1>Your Heart 💫</h1>
  <p>Your kindness makes the world beautiful.</p>
  <button onclick="nextSlide()">Almost There 🎁</button>
</div>

<div class="slide" id="slide5">
  <h1>One Last Surprise...</h1>
  <p>Are you ready? 🥰</p>
  <button onclick="finalReveal()">Reveal 🎉</button>
</div>

</div>

<div id="namePop"> HAPPY BIRTHDAY JYOSHTNA SRI 💖</div>

<div id="teddy">
  🧸
  <div class="balloon" style="left:-60px; top:-120px;">🎈</div>
  <div class="balloon" style="left:20px; top:-150px;">🎈</div>
  <div class="balloon" style="left:80px; top:-120px;">🎈</div>
</div>

<script>
let currentSlide = 1;
const totalSlides = 5;

/* Floating Hearts */
for(let i=0;i<20;i++){
  const heart=document.createElement("div");
  heart.className="heart";
  heart.innerHTML="💖";
  heart.style.left=Math.random()*100+"%";
  heart.style.fontSize=(Math.random()*20+15)+"px";
  heart.style.animationDuration=(Math.random()*5+5)+"s";
  document.body.appendChild(heart);
}

function nextSlide(){
  document.getElementById("slide"+currentSlide).classList.remove("active");
  currentSlide++;
  document.getElementById("slide"+currentSlide).classList.add("active");
  confetti({particleCount:60,spread:70});
}

function finalReveal(){
  document.getElementById("mainContainer").classList.add("hide");

  setTimeout(()=>{
    document.getElementById("namePop").classList.add("show");
    document.getElementById("teddy").classList.add("show");
  },800);

  confetti({particleCount:150,spread:100,origin:{y:0.6}});

  const duration=6000;
  const end=Date.now()+duration;
  const interval=setInterval(function(){
    if(Date.now()>end) return clearInterval(interval);
    confetti({
      particleCount:80,
      spread:360,
      origin:{x:Math.random(),y:Math.random()-0.2}
    });
  },300);
}
</script>

</body>
</html>
"""

file_path = Path("jyoshtna_sri_ultimate_surprise.html")
file_path.write_text(html_content, encoding="utf-8")
webbrowser.open(file_path.resolve().as_uri())