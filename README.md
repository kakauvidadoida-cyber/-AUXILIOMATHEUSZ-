<!DOCTYPE html>
<html lang="pt-br">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>AUXILIO MATHEUSZ</title>

<style>
:root{
  --bg:#000;
  --card:#0b0b0b;
  --line:#1a1a1a;
  --accent:#1f8bff;
  --text:#fff;
  --muted:#8f8f8f;
  --glow:0 0 14px rgba(31,139,255,.6);
}
*{box-sizing:border-box;font-family:Segoe UI,Roboto,Inter,sans-serif}
body{
  margin:0;
  min-height:100vh;
  background:radial-gradient(700px 350px at 50% -10%, #0e1826, transparent), var(--bg);
  display:flex;
  align-items:center;
  justify-content:center;
  color:var(--text);
}
.panel{
  width:360px;
  max-width:95%;
  background:linear-gradient(180deg,#0b0b0b,#050505);
  border-radius:18px;
  border:1px solid var(--line);
  box-shadow:0 25px 70px rgba(0,0,0,.9);
  overflow:hidden;
}
.header{
  padding:16px;
  display:flex;
  gap:12px;
  align-items:center;
  border-bottom:1px solid var(--line);
}
.logo{
  width:44px;height:44px;
  border-radius:12px;
  border:1px solid var(--accent);
  display:grid;place-items:center;
  color:var(--accent);
  font-weight:800;
  box-shadow:var(--glow);
}
.title b{display:block;font-size:15px}
.title small{font-size:12px;color:var(--muted)}
.body{padding:14px}

.item{
  background:#0a0a0a;
  border:1px solid var(--line);
  border-radius:14px;
  padding:12px;
  display:flex;
  align-items:center;
  justify-content:space-between;
  margin-bottom:10px;
}

.toggle{
  width:46px;height:26px;
  background:#111;
  border-radius:20px;
  position:relative;
  cursor:pointer;
}
.toggle::after{
  content:"";
  width:20px;height:20px;
  background:#555;
  border-radius:50%;
  position:absolute;
  top:3px;left:3px;
  transition:.25s;
}
.toggle.on{
  background:var(--accent);
  box-shadow:var(--glow);
}
.toggle.on::after{left:23px;background:#fff}

.select-box{
  display:flex;
  gap:10px;
  margin-bottom:12px;
}
.select{
  flex:1;
  text-align:center;
  padding:10px;
  border-radius:12px;
  border:1px solid var(--line);
  background:#0a0a0a;
  cursor:pointer;
  color:var(--muted);
}
.select.active{
  border-color:var(--accent);
  color:var(--accent);
  box-shadow:var(--glow);
}

.btn{
  width:100%;
  padding:12px;
  border-radius:14px;
  border:none;
  font-weight:700;
  cursor:pointer;
  margin-bottom:8px;
}
.btn.blue{
  background:var(--accent);
  color:#000;
  box-shadow:var(--glow);
}
.btn.dark{
  background:#111;
  color:#fff;
  border:1px solid var(--line);
}

.crash-box{
  display:none;
  background:#070707;
  border:1px solid var(--line);
  border-radius:14px;
  padding:12px;
  margin-top:10px;
}

/* MENSAGEM */
.message{
  position:fixed;
  top:20px;
  left:50%;
  transform:translateX(-50%);
  background:#0a0a0a;
  border:1px solid var(--accent);
  padding:12px 20px;
  border-radius:14px;
  box-shadow:var(--glow);
  font-weight:700;
  display:none;
  z-index:999;
}

.footer{
  text-align:center;
  font-size:12px;
  color:var(--muted);
  margin-top:6px;
}
</style>
</head>

<body>

<div class="message" id="messageBox"></div>

<div class="panel">
  <div class="header">
    <div class="logo">A</div>
    <div class="title">
      <b>AUXILIO MATHEUSZ</b>
      <small>Painel Externo</small>
    </div>
  </div>

  <div class="body">

    <div class="item"><span>AIMBOT</span><div class="toggle"></div></div>
    <div class="item"><span>NO RECOIL</span><div class="toggle"></div></div>
    <div class="item"><span>120 FPS</span><div class="toggle on"></div></div>

    <div class="item"><span>ALVO</span></div>
    <div class="select-box">
      <div class="select active">CABEÇA</div>
      <div class="select">PESCOÇO</div>
    </div>

    <button class="btn dark" id="openCrash">CRASH</button>

    <div class="crash-box" id="crashBox">
      <button class="btn dark" id="minimize">MINIMIZAR</button>
      <button class="btn blue" id="ativarBtn">ATIVAR</button>
      <button class="btn blue" id="injetarBtn">INJETAR</button>
    </div>

    <div class="footer">© MATHEUSZ</div>
  </div>
</div>

<script>
document.querySelectorAll('.toggle').forEach(t=>{
  t.onclick=()=>t.classList.toggle('on');
});

const selects=document.querySelectorAll('.select');
selects.forEach(s=>{
  s.onclick=()=>{
    selects.forEach(x=>x.classList.remove('active'));
    s.classList.add('active');
  }
});

const openCrash=document.getElementById('openCrash');
const crashBox=document.getElementById('crashBox');
const minimize=document.getElementById('minimize');
openCrash.onclick=()=>crashBox.style.display='block';
minimize.onclick=()=>crashBox.style.display='none';

const messageBox=document.getElementById('messageBox');
function showMessage(text){
  messageBox.textContent=text;
  messageBox.style.display='block';
  setTimeout(()=>messageBox.style.display='none',2500);
}
document.getElementById('injetarBtn').onclick=()=>showMessage('Injetado 💉');
document.getElementById('ativarBtn').onclick=()=>showMessage('ATIVO ⛹');
</script>

</body>
</html>
