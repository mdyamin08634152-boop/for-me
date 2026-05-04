<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Yamin ❤️ Kajol</title>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;1,300;1,400&family=Dancing+Script:wght@400;600&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }

  :root {
    --rose: #e8a0a0;
    --deep-rose: #c0626b;
    --blush: #f5dde0;
    --petal: #fdf0f2;
    --cream: #fff8f5;
    --text: #6b3a3f;
    --gold: #d4a574;
  }

  html, body {
    width: 100%; min-height: 100vh;
    background: var(--cream);
    font-family: 'Cormorant Garamond', serif;
    color: var(--text);
    overflow-x: hidden;
  }

  /* ── INTRO SPLASH ── */
  #splash {
    position: fixed; inset: 0; z-index: 999;
    background: linear-gradient(135deg, #fde8ec 0%, #fdf0f2 50%, #fde0e8 100%);
    display: flex; flex-direction: column;
    align-items: center; justify-content: center;
    cursor: pointer;
    transition: opacity 1s ease, visibility 1s ease;
  }
  #splash.hide { opacity: 0; visibility: hidden; pointer-events: none; }

  .splash-rose { font-size: 4rem; animation: pulse 2s infinite; }
  .splash-title {
    font-family: 'Dancing Script', cursive;
    font-size: clamp(2rem, 6vw, 3.5rem);
    color: var(--deep-rose);
    margin: 1rem 0 0.5rem;
    text-align: center;
  }
  .splash-hint {
    font-size: 1rem; color: var(--rose);
    letter-spacing: 0.15em; text-transform: uppercase;
    animation: blink 2s infinite;
  }

  @keyframes pulse { 0%,100%{transform:scale(1)} 50%{transform:scale(1.15)} }
  @keyframes blink { 0%,100%{opacity:1} 50%{opacity:0.3} }

  /* ── CANVAS (petals) ── */
  #petals { position: fixed; inset: 0; pointer-events: none; z-index: 0; }

  /* ── BACKGROUND ── */
  body::before {
    content: '';
    position: fixed; inset: 0; z-index: -1;
    background:
      radial-gradient(ellipse at 20% 20%, #fde8ec88 0%, transparent 60%),
      radial-gradient(ellipse at 80% 80%, #fce4ec88 0%, transparent 60%),
      linear-gradient(160deg, #fff8f5 0%, #fdf0f2 50%, #fff5f7 100%);
  }

  /* ── MAIN ── */
  main {
    position: relative; z-index: 1;
    display: flex; flex-direction: column;
    align-items: center;
    padding: 3rem 1.5rem 6rem;
    gap: 2.5rem;
  }

  /* ── HEADER ── */
  .header { text-align: center; }
  .header-sub {
    font-size: 0.85rem; letter-spacing: 0.3em;
    text-transform: uppercase; color: var(--rose);
    margin-bottom: 0.5rem;
  }
  .header-title {
    font-family: 'Dancing Script', cursive;
    font-size: clamp(2.5rem, 8vw, 5rem);
    color: var(--deep-rose);
    line-height: 1.1;
    text-shadow: 0 2px 20px #e8a0a040;
  }
  .header-heart {
    display: inline-block;
    animation: pulse 1.5s infinite;
    color: var(--deep-rose);
  }
  .header-tagline {
    font-style: italic;
    font-size: 1.15rem;
    color: var(--gold);
    margin-top: 0.5rem;
  }

  /* ── DIVIDER ── */
  .divider {
    display: flex; align-items: center; gap: 1rem;
    width: 100%; max-width: 400px;
  }
  .divider-line { flex: 1; height: 1px; background: linear-gradient(to right, transparent, var(--rose), transparent); }
  .divider-icon { color: var(--rose); font-size: 1.2rem; }

  /* ── TIMER CARD ── */
  .timer-card {
    background: rgba(255,255,255,0.7);
    backdrop-filter: blur(20px);
    border: 1px solid rgba(232,160,160,0.3);
    border-radius: 24px;
    padding: 2.5rem 2rem;
    text-align: center;
    width: 100%; max-width: 480px;
    box-shadow: 0 8px 40px rgba(192,98,107,0.1), inset 0 1px 0 rgba(255,255,255,0.8);
  }
  .timer-label {
    font-size: 0.8rem; letter-spacing: 0.25em;
    text-transform: uppercase; color: var(--rose);
    margin-bottom: 1.5rem;
  }
  .timer-grid {
    display: grid; grid-template-columns: repeat(4, 1fr);
    gap: 0.75rem; margin-bottom: 1rem;
  }
  .timer-unit { display: flex; flex-direction: column; align-items: center; gap: 0.3rem; }
  .timer-num {
    font-family: 'Cormorant Garamond', serif;
    font-size: clamp(2rem, 6vw, 3.2rem);
    font-weight: 300;
    color: var(--deep-rose);
    line-height: 1;
    min-width: 2ch; text-align: center;
  }
  .timer-unit-label {
    font-size: 0.7rem; letter-spacing: 0.2em;
    text-transform: uppercase; color: var(--rose);
  }
  .timer-sep { color: var(--rose); font-size: 2rem; align-self: flex-start; margin-top: 0.3rem; }
  .timer-date {
    font-style: italic; font-size: 0.95rem;
    color: var(--gold); margin-top: 0.5rem;
  }

  /* ── MUSIC PLAYER ── */
  .music-card {
    background: rgba(255,255,255,0.7);
    backdrop-filter: blur(20px);
    border: 1px solid rgba(232,160,160,0.3);
    border-radius: 20px;
    padding: 1.5rem 2rem;
    width: 100%; max-width: 480px;
    box-shadow: 0 8px 40px rgba(192,98,107,0.08);
    display: flex; flex-direction: column; align-items: center; gap: 1rem;
  }
  .music-title {
    font-family: 'Dancing Script', cursive;
    font-size: 1.4rem; color: var(--deep-rose);
  }
  .music-controls { display: flex; align-items: center; gap: 1.2rem; }
  .music-btn {
    width: 52px; height: 52px; border-radius: 50%;
    border: none; cursor: pointer;
    background: linear-gradient(135deg, var(--deep-rose), #e8829a);
    color: white; font-size: 1.3rem;
    display: flex; align-items: center; justify-content: center;
    box-shadow: 0 4px 20px rgba(192,98,107,0.35);
    transition: transform 0.2s, box-shadow 0.2s;
  }
  .music-btn:hover { transform: scale(1.08); box-shadow: 0 6px 28px rgba(192,98,107,0.45); }
  .music-waveform {
    display: flex; align-items: center; gap: 3px; height: 28px;
  }
  .wave-bar {
    width: 4px; border-radius: 4px;
    background: linear-gradient(to top, var(--rose), var(--deep-rose));
    animation: wave 1s ease-in-out infinite;
    transform-origin: bottom;
  }
  .wave-bar:nth-child(1){ height:10px; animation-delay:0s; }
  .wave-bar:nth-child(2){ height:20px; animation-delay:0.1s; }
  .wave-bar:nth-child(3){ height:14px; animation-delay:0.2s; }
  .wave-bar:nth-child(4){ height:24px; animation-delay:0.15s; }
  .wave-bar:nth-child(5){ height:18px; animation-delay:0.05s; }
  .wave-bar:nth-child(6){ height:10px; animation-delay:0.25s; }
  .wave-bar:nth-child(7){ height:22px; animation-delay:0.1s; }
  .wave-bar.paused { animation-play-state: paused; }
  @keyframes wave { 0%,100%{transform:scaleY(1)} 50%{transform:scaleY(0.4)} }

  .music-status { font-size: 0.8rem; color: var(--rose); letter-spacing: 0.1em; }

  /* ── QUOTE ── */
  .quote-card {
    background: rgba(255,255,255,0.5);
    border-left: 3px solid var(--rose);
    padding: 1.2rem 1.5rem;
    max-width: 420px; width: 100%;
    border-radius: 0 16px 16px 0;
  }
  .quote-text {
    font-style: italic; font-size: 1.1rem;
    color: var(--text); line-height: 1.7;
  }
  .quote-author { font-size: 0.85rem; color: var(--gold); margin-top: 0.5rem; text-align: right; }

  /* ── FLOATING HEARTS ── */
  .floating-hearts { position: fixed; inset: 0; pointer-events: none; z-index: 0; overflow: hidden; }
  .fheart {
    position: absolute; bottom: -40px;
    font-size: 1.2rem; opacity: 0;
    animation: floatUp linear infinite;
  }
  @keyframes floatUp {
    0% { transform: translateY(0) rotate(0deg); opacity: 0; }
    10% { opacity: 0.6; }
    90% { opacity: 0.3; }
    100% { transform: translateY(-110vh) rotate(30deg); opacity: 0; }
  }

  /* ── FOOTER ── */
  footer {
    position: relative; z-index: 1;
    text-align: center; padding: 2rem;
    font-style: italic; color: var(--rose);
    font-size: 0.9rem;
  }
</style>
</head>
<body>

<!-- SPLASH -->
<div id="splash">
  <div class="splash-rose">🌹</div>
  <div class="splash-title">Yamin ❤️ Kajol</div>
  <div class="splash-hint">Touch to enter ✨</div>
</div>

<!-- FLOATING HEARTS -->
<div class="floating-hearts" id="hearts"></div>

<!-- PETAL CANVAS -->
<canvas id="petals"></canvas>

<!-- HIDDEN AUDIO -->
<audio id="bgMusic" loop preload="auto">
  <source src="https://drive.google.com/uc?export=download&id=1kWzout8oNst9zzojx1_Zcvj7GpTisg3J" type="audio/mpeg">
</audio>

<main>
  <!-- HEADER -->
  <div class="header">
    <p class="header-sub">Our Love Story</p>
    <h1 class="header-title">Yamin <span class="header-heart">❤️</span> Kajol</h1>
    <p class="header-tagline">Every moment with you is a treasure</p>
  </div>

  <div class="divider">
    <div class="divider-line"></div>
    <div class="divider-icon">🌸</div>
    <div class="divider-line"></div>
  </div>

  <!-- TIMER -->
  <div class="timer-card">
    <p class="timer-label">We have been together for</p>
    <div class="timer-grid">
      <div class="timer-unit">
        <span class="timer-num" id="years">0</span>
        <span class="timer-unit-label">Years</span>
      </div>
      <div class="timer-unit">
        <span class="timer-num" id="months">0</span>
        <span class="timer-unit-label">Months</span>
      </div>
      <div class="timer-unit">
        <span class="timer-num" id="days">0</span>
        <span class="timer-unit-label">Days</span>
      </div>
      <div class="timer-unit">
        <span class="timer-num" id="hours">00</span>
        <span class="timer-unit-label">Hours</span>
      </div>
    </div>
    <div style="display:flex;justify-content:center;gap:1rem;margin-bottom:0.5rem;">
      <div class="timer-unit">
        <span class="timer-num" id="minutes">00</span>
        <span class="timer-unit-label">Minutes</span>
      </div>
      <div class="timer-unit">
        <span class="timer-num" id="seconds">00</span>
        <span class="timer-unit-label">Seconds</span>
      </div>
    </div>
    <p class="timer-date">Since August 8, 2025 🌹</p>
  </div>

  <!-- MUSIC PLAYER -->
  <div class="music-card">
    <div class="music-title">🎵 Our Song</div>
    <div class="music-controls">
      <div class="music-waveform" id="waveform">
        <div class="wave-bar paused"></div>
        <div class="wave-bar paused"></div>
        <div class="wave-bar paused"></div>
        <div class="wave-bar paused"></div>
        <div class="wave-bar paused"></div>
        <div class="wave-bar paused"></div>
        <div class="wave-bar paused"></div>
      </div>
      <button class="music-btn" id="playBtn" onclick="toggleMusic()">▶</button>
      <div class="music-waveform" id="waveform2">
        <div class="wave-bar paused"></div>
        <div class="wave-bar paused"></div>
        <div class="wave-bar paused"></div>
        <div class="wave-bar paused"></div>
        <div class="wave-bar paused"></div>
        <div class="wave-bar paused"></div>
        <div class="wave-bar paused"></div>
      </div>
    </div>
    <p class="music-status" id="musicStatus">Click ▶ to play our song 🎶</p>
  </div>

  <div class="divider">
    <div class="divider-line"></div>
    <div class="divider-icon">🌸</div>
    <div class="divider-line"></div>
  </div>

  <!-- QUOTE -->
  <div class="quote-card">
    <p class="quote-text">"You are my today and all of my tomorrows."</p>
    <p class="quote-author">— Leo Christopher</p>
  </div>
</main>

<footer>Made with love, for always 🌹</footer>

<script>
// ── SPLASH ──
document.getElementById('splash').addEventListener('click', () => {
  document.getElementById('splash').classList.add('hide');
  tryAutoPlay();
});

// ── MUSIC ──
const audio = document.getElementById('bgMusic');
let playing = false;

function tryAutoPlay() {
  audio.play().then(() => {
    playing = true;
    updateMusicUI();
  }).catch(() => {});
}

function toggleMusic() {
  if (playing) {
    audio.pause(); playing = false;
  } else {
    audio.play(); playing = true;
  }
  updateMusicUI();
}

function updateMusicUI() {
  document.getElementById('playBtn').textContent = playing ? '⏸' : '▶';
  document.getElementById('musicStatus').textContent = playing ? '♪ Playing our song...' : 'Click ▶ to play our song 🎶';
  document.querySelectorAll('.wave-bar').forEach(b => {
    if (playing) b.classList.remove('paused');
    else b.classList.add('paused');
  });
}

// ── COUNTDOWN ──
function updateTimer() {
  const start = new Date('2025-08-08T00:00:00');
  const now = new Date();
  let y = now.getFullYear() - start.getFullYear();
  let m = now.getMonth() - start.getMonth();
  let d = now.getDate() - start.getDate();
  if (d < 0) { m--; const prev = new Date(now.getFullYear(), now.getMonth(), 0); d += prev.getDate(); }
  if (m < 0) { y--; m += 12; }
  const totalMs = now - start;
  const totalSec = Math.floor(totalMs / 1000);
  const h = Math.floor((totalSec % 86400) / 3600);
  const min = Math.floor((totalSec % 3600) / 60);
  const sec = totalSec % 60;
  document.getElementById('years').textContent = y;
  document.getElementById('months').textContent = m;
  document.getElementById('days').textContent = d;
  document.getElementById('hours').textContent = String(h).padStart(2,'0');
  document.getElementById('minutes').textContent = String(min).padStart(2,'0');
  document.getElementById('seconds').textContent = String(sec).padStart(2,'0');
}
updateTimer();
setInterval(updateTimer, 1000);

// ── FLOATING HEARTS ──
const heartEmojis = ['❤️','🌸','💕','🌹','💖','✨','🩷'];
function spawnHeart() {
  const h = document.createElement('div');
  h.className = 'fheart';
  h.textContent = heartEmojis[Math.floor(Math.random()*heartEmojis.length)];
  h.style.left = Math.random()*100 + 'vw';
  h.style.fontSize = (0.8 + Math.random()*1.2) + 'rem';
  const dur = 6 + Math.random()*8;
  h.style.animationDuration = dur + 's';
  h.style.animationDelay = (Math.random()*3) + 's';
  document.getElementById('hearts').appendChild(h);
  setTimeout(() => h.remove(), (dur+3)*1000);
}
setInterval(spawnHeart, 800);
for(let i=0;i<8;i++) setTimeout(spawnHeart, i*300);

// ── PETAL CANVAS ──
const canvas = document.getElementById('petals');
const ctx = canvas.getContext('2d');
canvas.width = window.innerWidth;
canvas.height = window.innerHeight;
window.addEventListener('resize', () => { canvas.width=window.innerWidth; canvas.height=window.innerHeight; });

const petals = Array.from({length:25}, () => ({
  x: Math.random()*window.innerWidth,
  y: Math.random()*window.innerHeight - window.innerHeight,
  size: 6 + Math.random()*10,
  speed: 0.5 + Math.random()*1.5,
  drift: (Math.random()-0.5)*0.8,
  rot: Math.random()*Math.PI*2,
  rotSpeed: (Math.random()-0.5)*0.04,
  opacity: 0.3 + Math.random()*0.5
}));

function drawPetal(p) {
  ctx.save();
  ctx.translate(p.x, p.y);
  ctx.rotate(p.rot);
  ctx.globalAlpha = p.opacity;
  ctx.fillStyle = `hsl(${340 + Math.random()*20}, 70%, 80%)`;
  ctx.beginPath();
  ctx.ellipse(0, 0, p.size, p.size*0.6, 0, 0, Math.PI*2);
  ctx.fill();
  ctx.restore();
}

function animPetals() {
  ctx.clearRect(0,0,canvas.width,canvas.height);
  petals.forEach(p => {
    p.y += p.speed;
    p.x += p.drift;
    p.rot += p.rotSpeed;
    if (p.y > canvas.height+20) { p.y = -20; p.x = Math.random()*canvas.width; }
    drawPetal(p);
  });
  requestAnimationFrame(animPetals);
}
animPetals();
</script>
</body>
</html>

