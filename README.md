<a href="https://meusite.com">Para a ana</a>
Para uma pessoa queriada
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Uma pergunta para você ❤️</title>
<style>
  *{box-sizing:border-box;margin:0;padding:0}
  body{
    min-height:100vh; overflow:hidden; font-family:Arial, sans-serif;
    background:radial-gradient(circle at top,#ffb6c9 0,#ff6f9c 35%,#8e2b5d 100%);
    color:#fff; display:flex;align-items:center;justify-content:center;
  }
  .card{
    position:relative; z-index:5; width:min(92%,650px); padding:48px 30px;
    text-align:center; border:1px solid rgba(255,255,255,.35);
    background:rgba(255,255,255,.14); backdrop-filter:blur(15px);
    border-radius:30px; box-shadow:0 25px 80px rgba(60,0,30,.35);
  }
  .heart{font-size:64px;animation:pulse 1.5s infinite}
  h1{font-size:clamp(2rem,7vw,4rem);margin:12px 0}
  p{font-size:1.15rem;line-height:1.7;opacity:.95}
  .question{font-size:clamp(1.6rem,5vw,2.5rem);font-weight:800;margin:25px 0}
  .buttons{display:flex;justify-content:center;gap:18px;flex-wrap:wrap}
  button{
    border:0;border-radius:999px;padding:15px 30px;font-size:1.1rem;font-weight:bold;
    cursor:pointer;transition:.25s;box-shadow:0 8px 25px rgba(0,0,0,.2)
  }
  #yes{background:#fff;color:#e52f6d}
  #yes:hover{transform:scale(1.08)}
  #no{background:rgba(255,255,255,.2);color:#fff;position:relative}
  .hint{font-size:.85rem;margin-top:18px;opacity:.75}
  .floating{position:fixed;bottom:-50px;font-size:25px;animation:float 8s linear infinite;opacity:.7}
  .success{display:none}
  .success h2{font-size:clamp(2.2rem,8vw,4rem);margin-bottom:15px}
  .sparkle{position:fixed;pointer-events:none;animation:boom 1.8s forwards}
  @keyframes pulse{50%{transform:scale(1.15)}}
  @keyframes float{to{transform:translateY(-110vh) rotate(360deg);opacity:0}}
  @keyframes boom{0%{transform:scale(.2);opacity:1}100%{transform:translate(var(--x),var(--y)) scale(1.3);opacity:0}}
</style>
</head>
<body>
<div class="card" id="card">
  <div class="main">
    <div class="heart">❤️</div>
    <h1>Tenho uma pergunta...</h1>
    <p>
      Desde que você apareceu, meus dias ficaram mais bonitos,
      meus dia começou a ficar melhor 
    </p>
    <div class="question">Quer namorar comigo? 🥰</div>
    <div class="buttons">
      <button id="yes">SIM! ❤️</button>
      <button id="no">Não 😅</button>
    </div>
    <div class="hint"> pense com carinho antes de responder 👀</div>
  </div>

  <div class="success">
    <div class="heart">💖</div>
    <h2>EU SABIA! 🥹</h2>
    <p>Agora oficialmente você e so minha agora kkkkk ❤️<br><br>
    Prometo fazer o possível para transformar cada dia em uma lembrança bonita.</p>
    <div style="font-size:42px;margin-top:22px">💐💍✨🥰</div>
  </div>
</div>

<script>
const no=document.getElementById('no');
const yes=document.getElementById('yes');
const main=document.querySelector('.main');
const success=document.querySelector('.success');

function moveNo(){
  const maxX=Math.max(30, window.innerWidth/2-100);
  const maxY=Math.max(30, window.innerHeight/2-80);
  no.style.position='fixed';
  no.style.left=(Math.random()*maxX + 30)+'px';
  no.style.top=(Math.random()*maxY + 30)+'px';
}
no.addEventListener('mouseenter',moveNo);
no.addEventListener('touchstart',(e)=>{e.preventDefault();moveNo()});

yes.addEventListener('click',()=>{
  main.style.display='none';
  success.style.display='block';
  for(let i=0;i<45;i++){
    const s=document.createElement('div');
    s.className='sparkle';
    s.textContent=['❤️','💖','💕','✨','💗'][Math.floor(Math.random()*5)];
    s.style.left='50%'; s.style.top='50%';
    s.style.setProperty('--x',(Math.random()*1000-500)+'px');
    s.style.setProperty('--y',(Math.random()*800-400)+'px');
    s.style.fontSize=(18+Math.random()*28)+'px';
    document.body.appendChild(s);
    setTimeout(()=>s.remove(),1800);
  }
});

for(let i=0;i<18;i++){
  const h=document.createElement('div');
  h.className='floating';
  h.textContent=['❤️','💕','💗','💖'][i%4];
  h.style.left=Math.random()*100+'vw';
  h.style.animationDelay=Math.random()*7+'s';
  h.style.animationDuration=(6+Math.random()*7)+'s';
  document.body.appendChild(h);
}
</script>
</body>
</html>
