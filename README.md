
<!DOCTYPE html>
<html lang="bn">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>SUPER GAMES 100+</title>
<style>
*{box-sizing:border-box}
body{margin:0;background:#101426;color:white;font-family:Arial,sans-serif;padding:20px}
header{text-align:center;color:#ffd43b}
h1{font-size:28px}
p{color:#c5c9d8}
.card{background:#202945;border-radius:18px;padding:18px;margin:14px 0}
button{border:0;border-radius:12px;padding:13px;background:#ffd43b;color:#171717;font-size:16px;font-weight:bold;margin:5px;cursor:pointer}
button:active{transform:scale(.97)}
#game{text-align:center}
#score{color:#ffd43b;font-size:24px}
</style>
</head>
<body>
<header>
<h1>🎮 SUPER GAMES 100+</h1>
<p>এক অ্যাপে অনেক মজার গেম!</p>
</header>

<div class="card">
<h2>🔥 Mini Games</h2>
<p>তোমার পছন্দের গেম বেছে নাও।</p>
<button onclick="startTap()">🎯 Tap Game</button>
<button onclick="startGuess()">🔢 Guess Number</button>
<button onclick="startRPS()">✊ Rock Paper Scissors</button>
</div>

<div class="card" id="game">
<h2>স্বাগতম!</h2>
<p>উপরের একটি গেম বেছে নাও।</p>
</div>

<script>
const game=document.getElementById('game');
let score=0,secret=0;

function startTap(){
score=0;
game.innerHTML=`
<h2>🎯 Tap Game</h2>
<p>যতবার পারো বোতাম চাপো!</p>
<p id="score">Score: 0</p>
<button onclick="score++;document.getElementById('score').textContent='Score: '+score">TAP!</button>`;
}

function startGuess(){
secret=Math.floor(Math.random()*10)+1;
game.innerHTML=`
<h2>🔢 Guess Number</h2>
<p>১ থেকে ১০-এর মধ্যে সংখ্যা অনুমান করো।</p>
<input id="guess" type="number" min="1" max="10"
style="padding:12px;width:100%;border-radius:10px">
<button onclick="checkGuess()">Check</button>
<p id="result"></p>`;
}

function checkGuess(){
const n=Number(document.getElementById('guess').value);
const result=document.getElementById('result');
if(n===secret){
result.textContent='🎉 সঠিক উত্তর! জিতে গেছ!';
}else{
result.textContent=n<secret?'আরও বড় সংখ্যা দাও!':'আরও ছোট সংখ্যা দাও!';
}
}

function startRPS(){
game.innerHTML=`
<h2>✊ Rock Paper Scissors</h2>
<p>তোমার পছন্দ বেছে নাও।</p>
<button onclick="play('Rock')">✊ Rock</button>
<button onclick="play('Paper')">✋ Paper</button>
<button onclick="play('Scissors')">✌️ Scissors</button>
<p id="result"></p>`;
}

function play(choice){
const options=['Rock','Paper','Scissors'];
const bot=options[Math.floor(Math.random()*3)];
let msg=choice===bot?'ড্র!':(
(choice==='Rock'&&bot==='Scissors')||
(choice==='Paper'&&bot==='Rock')||
(choice==='Scissors'&&bot==='Paper')
?'তুমি জিতেছ! 🎉':'কম্পিউটার জিতেছে!');
document.getElementById('result').textContent=
'তুমি: '+choice+' | কম্পিউটার: '+bot+' — '+msg;
}
</script>
</body>
</html>
# super-games-100
My mobile gaming project - SUPER GAMES 100+
