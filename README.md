# rock-paper-scissors
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<title>Rock Paper Scissors</title>
<style>
body{margin:0;min-height:100vh;display:grid;place-items:center;background:#17152b;color:white;font-family:Arial;text-align:center;padding:20px}
.game{max-width:500px;width:100%;padding:25px;background:#262341;border-radius:20px;border:1px solid #49416e}
.choices{display:flex;justify-content:center;gap:12px;flex-wrap:wrap;margin:25px 0}
button{font-size:24px;padding:17px;border:0;border-radius:12px;background:#e9d5ff;cursor:pointer}
button:hover{transform:translateY(-3px)}
#result{font-size:21px;min-height:55px}
.score{display:flex;justify-content:space-around;background:#19172e;border-radius:12px;padding:15px}
.reset{font-size:15px;background:#a78bfa;margin-top:15px}
</style>
</head>
<body>
<main class="game">
<h1>✊ Rock Paper Scissors</h1>
<p>Choose your move and challenge the computer.</p>
<div class="choices">
<button onclick="play('Rock')" aria-label="Choose Rock">✊</button>
<button onclick="play('Paper')" aria-label="Choose Paper">✋</button>
<button onclick="play('Scissors')" aria-label="Choose Scissors">✌️</button>
</div>
<div id="moves">Your move vs Computer</div>
<h2 id="result">Make your first move!</h2>
<div class="score">
<div>You <h2 id="you">0</h2></div>
<div>Computer <h2 id="computer">0</h2></div>
</div>
<button class="reset" onclick="resetGame()">Reset Game</button>
</main>
<script>
let you=0,computer=0;
function play(choice){
const options=["Rock","Paper","Scissors"];
const opponent=options[Math.floor(Math.random()*3)];
let message;
if(choice===opponent){
message="It's a draw!";
}else if(
(choice==="Rock"&&opponent==="Scissors")||
(choice==="Paper"&&opponent==="Rock")||
(choice==="Scissors"&&opponent==="Paper")
){
message="You win this round!";
you++;
}else{
message="Computer wins this round!";
computer++;
}
document.getElementById("moves").textContent=`You chose ${choice} · Computer chose ${opponent}`;
document.getElementById("result").textContent=message;
document.getElementById("you").textContent=you;
document.getElementById("computer").textContent=computer;
}
function resetGame(){
you=0;computer=0;
document.getElementById("you").textContent="0";
document.getElementById("computer").textContent="0";
document.getElementById("moves").textContent="Your move vs Computer";
document.getElementById("result").textContent="Make your first move!";
}
</script>
</body>
</html>
