<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>✨ Генератор Хвальбы ✨</title>
<style>
  @import url('https://cdn.fontsource.com/css/fontsource/nunito.css');

  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  body {
    font-family: 'Nunito', sans-serif;
    min-height: 100vh;
    overflow-x: hidden;
    background: linear-gradient(135deg, #ffe0ec, #ffd6e8, #fce4f0, #f0d4f0, #e8d0f8);
    background-size: 400% 400%;
    animation: bgShift 15s ease infinite;
    position: relative;
  }

  @keyframes bgShift {
    0%, 100% { background-position: 0% 50%; }
    50% { background-position: 100% 50%; }
  }

  /* Paw print background pattern */
  .paw-bg {
    position: fixed;
    top: 0; left: 0; right: 0; bottom: 0;
    background-image: url('https://image.qwenlm.ai/public_source/98478960-0b4b-4f2c-abd0-16e0c3162d65/111a4ef00-d058-483b-bbdc-243040181f9d.png');
    background-size: 120px;
    opacity: 0.12;
    pointer-events: none;
    z-index: 0;
  }

  /* Sparkle particles */
  .sparkle-container {
    position: fixed;
    top: 0; left: 0; right: 0; bottom: 0;
    pointer-events: none;
    z-index: 1;
    overflow: hidden;
  }

  .sparkle {
    position: absolute;
    width: 6px;
    height: 6px;
    background: radial-gradient(circle, #fff 0%, transparent 70%);
    border-radius: 50%;
    animation: sparkleAnim var(--dur) ease-in-out infinite;
    animation-delay: var(--delay);
  }

  @keyframes sparkleAnim {
    0%, 100% { opacity: 0; transform: scale(0) rotate(0deg); }
    50% { opacity: 1; transform: scale(1) rotate(180deg); }
  }

  .sparkle::before,
  .sparkle::after {
    content: '';
    position: absolute;
    background: #ffb6d9;
    border-radius: 50%;
  }

  .sparkle::before {
    width: 2px;
    height: 12px;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
  }

  .sparkle::after {
    width: 12px;
    height: 2px;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
  }

  .sparkle.gold {
    background: radial-gradient(circle, #fff8cc 0%, transparent 70%);
  }
  .sparkle.gold::before,
  .sparkle.gold::after {
    background: #ffd700;
  }

  .sparkle.pink {
    background: radial-gradient(circle, #fff 0%, transparent 70%);
  }
  .sparkle.pink::before,
  .sparkle.pink::after {
    background: #ff69b4;
  }

  .sparkle.rainbow::before { background: #ff6b6b; }
  .sparkle.rainbow::after { background: #ffd93d; }

  /* Main container */
  .main-container {
    position: relative;
    z-index: 10;
    display: flex;
    flex-direction: column;
    align-items: center;
    min-height: 100vh;
    padding: 30px 20px;
  }

  /* Rainbow top bar */
  .rainbow-bar {
    width: 100%;
    max-width: 900px;
    height: 8px;
    border-radius: 4px;
    background: linear-gradient(90deg, #ff6b6b, #ffa500, #ffd93d, #6bcb77, #4d96ff, #9b59b6, #ff6b9d);
    background-size: 200% 100%;
    animation: rainbowMove 3s linear infinite;
    margin-bottom: 20px;
    box-shadow: 0 0 20px rgba(255, 107, 157, 0.5);
  }

  @keyframes rainbowMove {
    0% { background-position: 0% 0; }
    100% { background-position: 200% 0; }
  }

  /* Header */
  .header {
    text-align: center;
    margin-bottom: 25px;
  }

  .header h1 {
    font-size: 2.8em;
    background: linear-gradient(135deg, #ff6b9d, #c44dff, #ff6b9d, #ff8ec4);
    background-size: 200% auto;
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    animation: shimmerText 3s ease infinite;
    text-shadow: none;
    filter: drop-shadow(0 2px 10px rgba(255, 107, 157, 0.3));
    line-height: 1.3;
  }

  @keyframes shimmerText {
    0%, 100% { background-position: 0% center; }
    50% { background-position: 200% center; }
  }

  .header .subtitle {
    font-size: 1.1em;
    color: #d4739a;
    margin-top: 8px;
    font-weight: 600;
  }

  .header .emoji-deco {
    font-size: 1.5em;
  }

  /* Unicorn decorations */
  .unicorn-deco {
    position: fixed;
    z-index: 5;
    pointer-events: none;
    opacity: 0.2;
    animation: floatUnicorn 20s ease-in-out infinite;
  }

  .unicorn-deco.left {
    top: 20%;
    left: -30px;
    width: 150px;
  }

  .unicorn-deco.right {
    bottom: 20%;
    right: -30px;
    width: 150px;
    transform: scaleX(-1);
  }

  @keyframes floatUnicorn {
    0%, 100% { transform: translateY(0); }
    50% { transform: translateY(-20px); }
  }

  /* Kitten image section */
  .kitten-section {
    position: relative;
    margin: 10px 0 20px;
  }

  .kitten-img {
    width: 220px;
    height: 220px;
    object-fit: cover;
    border-radius: 50%;
    border: 5px solid rgba(255, 182, 217, 0.6);
    box-shadow:
      0 0 30px rgba(255, 107, 157, 0.4),
      0 0 60px rgba(255, 107, 157, 0.2),
      inset 0 0 30px rgba(255, 255, 255, 0.1);
    animation: kittenPulse 4s ease-in-out infinite;
    transition: transform 0.3s ease;
  }

  .kitten-img:hover {
    transform: scale(1.05) rotate(3deg);
  }

  @keyframes kittenPulse {
    0%, 100% { box-shadow: 0 0 30px rgba(255, 107, 157, 0.4), 0 0 60px rgba(255, 107, 157, 0.2); }
    50% { box-shadow: 0 0 50px rgba(255, 107, 157, 0.6), 0 0 100px rgba(255, 107, 157, 0.3), 0 0 150px rgba(255, 107, 157, 0.1); }
  }

  .kitten-sparkle-ring {
    position: absolute;
    top: -10px; left: -10px; right: -10px; bottom: -10px;
    border-radius: 50%;
    border: 2px dashed rgba(255, 215, 0, 0.4);
    animation: ringSpin 10s linear infinite;
  }

  @keyframes ringSpin {
    from { transform: rotate(0deg); }
    to { transform: rotate(360deg); }
  }

  /* Praise box */
  .praise-box {
    background: linear-gradient(135deg, rgba(255, 255, 255, 0.85), rgba(255, 228, 240, 0.9));
    backdrop-filter: blur(15px);
    border-radius: 30px;
    padding: 35px 45px;
    max-width: 700px;
    width: 100%;
    min-height: 140px;
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
    margin-bottom: 25px;
    border: 3px solid rgba(255, 182, 217, 0.5);
    box-shadow:
      0 10px 40px rgba(255, 107, 157, 0.15),
      0 0 0 1px rgba(255, 255, 255, 0.5),
      inset 0 1px 0 rgba(255, 255, 255, 0.8);
    position: relative;
    overflow: hidden;
  }

  .praise-box::before {
    content: '';
    position: absolute;
    top: -2px; left: -2px; right: -2px; bottom: -2px;
    border-radius: 31px;
    background: linear-gradient(45deg, #ff6b9d, #c44dff, #ff8ec4, #ffd700, #ff6b9d, #c44dff);
    background-size: 300% 300%;
    animation: borderGlow 4s ease infinite;
    z-index: -1;
    opacity: 0.6;
  }

  @keyframes borderGlow {
    0%, 100% { background-position: 0% 50%; }
    50% { background-position: 100% 50%; }
  }

  .praise-text {
    font-size: 1.6em;
    color: #8b3a6a;
    font-weight: 700;
    line-height: 1.5;
    transition: opacity 0.3s ease;
    position: relative;
    z-index: 1;
  }

  .praise-text.fade {
    opacity: 0;
  }

  .praise-text .highlight {
    background: linear-gradient(135deg, #ff6b9d, #c44dff);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  /* Counter */
  .counter {
    display: flex;
    align-items: center;
    gap: 10px;
    margin-bottom: 20px;
    color: #c47aad;
    font-weight: 600;
    font-size: 1.05em;
  }

  .counter-badge {
    background: linear-gradient(135deg, #ffb6d9, #e89ec4);
    color: white;
    padding: 5px 14px;
    border-radius: 20px;
    font-weight: 800;
    box-shadow: 0 3px 10px rgba(255, 107, 157, 0.3);
  }

  /* Button */
  .praise-btn {
    position: relative;
    padding: 18px 55px;
    font-size: 1.5em;
    font-family: 'Nunito', sans-serif;
    font-weight: 800;
    color: white;
    border: none;
    border-radius: 50px;
    cursor: pointer;
    background: linear-gradient(135deg, #ff6b9d, #e84a9c, #c44dff, #ff6b9d);
    background-size: 300% 300%;
    animation: btnGradient 4s ease infinite;
    box-shadow:
      0 8px 25px rgba(255, 107, 157, 0.5),
      0 0 0 0 rgba(255, 107, 157, 0.4);
    transition: all 0.3s ease;
    overflow: hidden;
    letter-spacing: 1px;
  }

  @keyframes btnGradient {
    0%, 100% { background-position: 0% 50%; }
    50% { background-position: 100% 50%; }
  }

  .praise-btn:hover {
    transform: translateY(-3px) scale(1.03);
    box-shadow:
      0 12px 35px rgba(255, 107, 157, 0.6),
      0 0 60px rgba(255, 107, 157, 0.3);
  }

  .praise-btn:active {
    transform: translateY(0) scale(0.97);
  }

  .praise-btn::after {
    content: '';
    position: absolute;
    top: -50%;
    left: -50%;
    width: 200%;
    height: 200%;
    background: linear-gradient(
      45deg,
      transparent 30%,
      rgba(255, 255, 255, 0.3) 50%,
      transparent 70%
    );
    animation: btnShine 3s ease infinite;
  }

  @keyframes btnShine {
    0% { transform: translateX(-100%) rotate(45deg); }
    100% { transform: translateX(100%) rotate(45deg); }
  }

  .praise-btn .btn-text {
    position: relative;
    z-index: 2;
  }

  .praise-btn .btn-emoji {
    margin-right: 8px;
    font-size: 0.85em;
  }

  /* Explosion effect */
  .explosion-container {
    position: fixed;
    top: 0; left: 0; right: 0; bottom: 0;
    pointer-events: none;
    z-index: 100;
  }

  .burst-particle {
    position: absolute;
    font-size: 1.5em;
    animation: burstAnim 1.2s ease-out forwards;
  }

  @keyframes burstAnim {
    0% {
      opacity: 1;
      transform: translate(0, 0) scale(1) rotate(0deg);
    }
    100% {
      opacity: 0;
      transform: translate(var(--tx), var(--ty)) scale(0.3) rotate(720deg);
    }
  }

  /* Floating hearts */
  .floating-hearts {
    position: fixed;
    top: 0; left: 0; right: 0; bottom: 0;
    pointer-events: none;
    z-index: 2;
    overflow: hidden;
  }

  .float-heart {
    position: absolute;
    font-size: 1.2em;
    animation: floatHeart var(--dur) ease-in-out infinite;
    animation-delay: var(--delay);
    opacity: 0.3;
  }

  @keyframes floatHeart {
    0% { transform: translateY(100vh) rotate(0deg); opacity: 0; }
    10% { opacity: 0.3; }
    90% { opacity: 0.3; }
    100% { transform: translateY(-50px) rotate(360deg); opacity: 0; }
  }

  /* Unicorn bottom decoration */
  .unicorn-bottom {
    position: relative;
    margin-top: 25px;
    text-align: center;
  }

  .unicorn-bottom img {
    width: 120px;
    opacity: 0.5;
    filter: drop-shadow(0 0 20px rgba(255, 107, 157, 0.3));
    animation: unicornBob 5s ease-in-out infinite;
  }

  @keyframes unicornBob {
    0%, 100% { transform: translateY(0) rotate(-3deg); }
    50% { transform: translateY(-10px) rotate(3deg); }
  }

  .unicorn-bottom-text {
    color: #d4739a;
    font-size: 0.95em;
    margin-top: 8px;
    font-weight: 600;
  }

  /* Paw prints trail */
  .paw-trail {
    position: fixed;
    bottom: 20px;
    left: 0;
    right: 0;
    display: flex;
    justify-content: center;
    gap: 40px;
    pointer-events: none;
    z-index: 2;
    opacity: 0.2;
  }

  .paw-icon {
    font-size: 1.8em;
    color: #ff6b9d;
    animation: pawBounce 2s ease-in-out infinite;
  }

  .paw-icon:nth-child(2) { animation-delay: 0.2s; }
  .paw-icon:nth-child(3) { animation-delay: 0.4s; }
  .paw-icon:nth-child(4) { animation-delay: 0.6s; }
  .paw-icon:nth-child(5) { animation-delay: 0.8s; }

  @keyframes pawBounce {
    0%, 100% { transform: translateY(0); }
    50% { transform: translateY(-8px); }
  }

  /* Kitten paws near button */
  .kitten-paws {
    position: absolute;
    bottom: -30px;
    display: flex;
    gap: 60px;
  }

  .kitten-paw {
    width: 30px;
    height: 25px;
    background: radial-gradient(circle, #ffb6d9 60%, transparent 61%);
    border-radius: 50%;
    opacity: 0.6;
    animation: pawTwitch 1.5s ease-in-out infinite;
  }

  .kitten-paw:nth-child(2) { animation-delay: 0.3s; }

  @keyframes pawTwitch {
    0%, 100% { transform: scale(1); }
    50% { transform: scale(1.15); }
  }

  /* Mood selector */
  .mood-section {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    justify-content: center;
    margin-bottom: 20px;
    max-width: 600px;
  }

  .mood-btn {
    padding: 8px 20px;
    border: 2px solid rgba(255, 182, 217, 0.5);
    background: rgba(255, 255, 255, 0.6);
    border-radius: 25px;
    font-family: 'Nunito', sans-serif;
    font-weight: 700;
    font-size: 0.9em;
    color: #b5638a;
    cursor: pointer;
    transition: all 0.3s ease;
  }

  .mood-btn:hover {
    background: rgba(255, 182, 217, 0.3);
    border-color: #ff6b9d;
    transform: scale(1.05);
  }

  .mood-btn.active {
    background: linear-gradient(135deg, #ff6b9d, #c44dff);
    color: white;
    border-color: transparent;
    box-shadow: 0 4px 15px rgba(255, 107, 157, 0.4);
  }

  /* Glitter canvas overlay */
  #glitterCanvas {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    pointer-events: none;
    z-index: 3;
  }

  /* Star rating / mood display */
  .love-meter {
    display: flex;
    align-items: center;
    gap: 8px;
    margin-bottom: 15px;
    color: #d4739a;
    font-weight: 600;
  }

  .love-hearts {
    display: flex;
    gap: 3px;
  }

  .love-heart {
    font-size: 1.3em;
    transition: all 0.3s ease;
    opacity: 0.3;
  }

  .love-heart.filled {
    opacity: 1;
    animation: heartPop 0.4s ease;
  }

  @keyframes heartPop {
    0% { transform: scale(0.5); }
    50% { transform: scale(1.3); }
    100% { transform: scale(1); }
  }

  /* Responsive */
  @media (max-width: 600px) {
    .header h1 { font-size: 1.9em; }
    .praise-text { font-size: 1.2em; }
    .praise-btn { padding: 15px 40px; font-size: 1.2em; }
    .praise-box { padding: 25px 25px; }
    .kitten-img { width: 160px; height: 160px; }
    .unicorn-deco { width: 100px; }
  }

  /* Glitter burst on praise */
  .glitter-burst {
    position: fixed;
    width: 8px;
    height: 8px;
    border-radius: 50%;
    pointer-events: none;
    z-index: 200;
    animation: glitterBurst 0.8s ease-out forwards;
  }

  @keyframes glitterBurst {
    0% { opacity: 1; transform: translate(0, 0) scale(1); }
    100% { opacity: 0; transform: translate(var(--gx), var(--gy)) scale(0); }
  }

  /* Tooltip for kitten */
  .kitten-tooltip {
    position: absolute;
    top: -40px;
    left: 50%;
    transform: translateX(-50%);
    background: rgba(255, 255, 255, 0.9);
    color: #c44dff;
    padding: 5px 15px;
    border-radius: 15px;
    font-size: 0.85em;
    font-weight: 700;
    white-space: nowrap;
    opacity: 0;
    transition: opacity 0.3s;
    pointer-events: none;
    border: 2px solid rgba(255, 182, 217, 0.5);
  }

  .kitten-section:hover .kitten-tooltip {
    opacity: 1;
  }

  /* History section */
  .history-section {
    margin-top: 30px;
    width: 100%;
    max-width: 700px;
  }

  .history-toggle {
    background: none;
    border: none;
    color: #c47aad;
    font-family: 'Nunito', sans-serif;
    font-weight: 700;
    font-size: 1em;
    cursor: pointer;
    display: flex;
    align-items: center;
    gap: 8px;
    margin: 0 auto;
    padding: 8px 20px;
    border-radius: 20px;
    transition: all 0.3s;
  }

  .history-toggle:hover {
    background: rgba(255, 182, 217, 0.2);
  }

  .history-list {
    max-height: 0;
    overflow: hidden;
    transition: max-height 0.5s ease;
  }

  .history-list.open {
    max-height: 500px;
    overflow-y: auto;
  }

  .history-item {
    padding: 12px 20px;
    margin: 8px 0;
    background: rgba(255, 255, 255, 0.5);
    border-radius: 15px;
    color: #8b3a6a;
    font-size: 0.95em;
    border-left: 3px solid #ffb6d9;
    animation: slideIn 0.3s ease;
  }

  @keyframes slideIn {
    from { opacity: 0; transform: translateX(-20px); }
    to { opacity: 1; transform: translateX(0); }
  }

  /* Scrollbar */
  .history-list::-webkit-scrollbar {
    width: 6px;
  }
  .history-list::-webkit-scrollbar-track {
    background: transparent;
  }
  .history-list::-webkit-scrollbar-thumb {
    background: rgba(255, 182, 217, 0.5);
    border-radius: 3px;
  }
</style>
</head>
<body>

<div class="paw-bg"></div>

<div class="sparkle-container" id="sparkleContainer"></div>

<div class="floating-hearts" id="floatingHearts"></div>

<canvas id="glitterCanvas"></canvas>

<!-- Unicorn decorations -->
<img class="unicorn-deco left" src="https://image.qwenlm.ai/public_source/98478960-0b4b-4f2c-abd0-16e0c3162d65/1d8ef0147-7ffc-4713-a2e5-c50a8cb2db60.png" alt="unicorn">
<img class="unicorn-deco right" src="https://image.qwenlm.ai/public_source/98478960-0b4b-4f2c-abd0-16e0c3162d65/1d8ef0147-7ffc-4713-a2e5-c50a8cb2db60.png" alt="unicorn">

<div class="main-container">
  <div class="rainbow-bar"></div>

  <div class="header">
    <h1>✨ Генератор Хвальбы ✨</h1>
    <p class="subtitle"><span class="emoji-deco"></span> Ты заслуживаешь комплиментов! <span class="emoji-deco">🦄</span></p>
  </div>

  <div class="kitten-section">
    <div class="kitten-sparkle-ring"></div>
    <img class="kitten-img" src="https://image.qwenlm.ai/public_source/98478960-0b4b-4f2c-abd0-16e0c3162d65/1cc400312-298d-40b7-b266-0ef26ff4f7c8.png" alt="Розовый котёнок">
    <div class="kitten-tooltip">Мяу! Ты чудесный! 💖</div>
  </div>

  <div class="mood-section">
    <button class="mood-btn active" data-mood="all" onclick="setMood('all')">🌈 Все</button>
    <button class="mood-btn" data-mood="sweet" onclick="setMood('sweet')">🍬 Мило</button>
    <button class="mood-btn" data-mood="funny" onclick="setMood('funny')">😄 Смешно</button>
    <button class="mood-btn" data-mood="epic" onclick="setMood('epic')">⚡ Эпично</button>
    <button class="mood-btn" data-mood="kitten" onclick="setMood('kitten')">🐱 Котята</button>
  </div>

  <div class="love-meter">
    <span>Уровень счастья:</span>
    <div class="love-hearts" id="loveHearts">
      <span class="love-heart">💖</span>
      <span class="love-heart">💖</span>
      <span class="love-heart">💖</span>
      <span class="love-heart">💖</span>
      <span class="love-heart">💖</span>
    </div>
  </div>

  <div class="counter">
    <span>Хвальбы получено:</span>
    <span class="counter-badge" id="counterBadge">0</span>
  </div>

  <div class="praise-box" id="praiseBox">
    <p class="praise-text" id="praiseText">
      Нажми на кнопку и получи свою порцию хвальбы! 🌸✨
    </p>
  </div>

  <button class="praise-btn" id="praiseBtn" onclick="generatePraise()">
    <span class="btn-text"><span class="btn-emoji"></span> ПОХВАЛИ МЕНЯ</span>
  </button>

  <div class="unicorn-bottom">
    <img src="https://image.qwenlm.ai/public_source/98478960-0b4b-4f2c-abd0-16e0c3162d65/1d8ef0147-7ffc-4713-a2e5-c50a8cb2db60.png" alt="unicorn">
    <p class="unicorn-bottom-text">🌈 Единороги гордятся тобой 🌈</p>
  </div>

  <div class="history-section">
    <button class="history-toggle" onclick="toggleHistory()">
      <span id="historyArrow">▶</span> История хвальбы
    </button>
    <div class="history-list" id="historyList"></div>
  </div>
</div>

<div class="paw-trail">
  <span class="paw-icon"></span>
  <span class="paw-icon">🐾</span>
  <span class="paw-icon">🐾</span>
  <span class="paw-icon"></span>
  <span class="paw-icon">🐾</span>
</div>

<div class="explosion-container" id="explosionContainer"></div>

<script>
const praisePhrases = {
  all: [
    "Ты невероятно прекрасный человек! 🌟",
    "Мир стал лучше, потому что в нём есть ты! 🌍💖",
    "Твоя улыбка освещает целые галактики! ✨",
    "Ты — самый сияющий единорог в стаде! 🦄",
    "Ты заслуживаешь всех радуг мира! 🌈",
    "Твоё сердце настолько доброе, что котята мурчат от счастья! 🐱💕",
    "Ты красивее всех закатов! 🌅",
    "Даже единороги завидуют твоей крутости! 🦄✨",
    "Ты — причина, по которой блестки существуют! 💎",
    "Если бы доброта была валютой, ты был бы миллиардером! 💰💖",
    "Ты сияешь ярче тысячи звёзд! ⭐",
    "Ты — волшебство, которое мир заслужил! ✨",
    "Твой внутренний свет делает этот мир прекраснее! ",
    "Ты настолько крут, что котята хотят быть как ты! 🐱👑",
    "Ты — радуга в чей-то пасмурный день! 🌈☀️",
    "Ты заслуживаешь миллион обнимашек! 🤗💖",
    "Ты — звезда первой величины! 🌟",
    "Твоя энергия заряжает всех вокруг! ⚡💕",
    "Ты — лучшее, что случалось с этим днём! ",
    "Ты такой классный, что даже котёнок на фото завидует! 🐱😻",
    "Ты — персик среди всех фруктов! 🍑✨",
    "Ты вдохновляешь единорогов на подвиги! 🦄",
    "Ты — ходячий генератор позитива! 😄💖",
    "Твоя доброта бесконечна, как космос! 🌌💕",
    "Ты — бриллиант среди камней! 💎✨",
    "Даже радуга хочет быть такой же красивой, как ты! 🌈💖",
    "Ты — самый сладкий зефир в коробке! 🍬💕",
    "Ты делаешь этот мир волшебнее! 🪄✨",
    "Ты — тот самый человек, о котором мечтают котята! 🐱💫",
    "Ты сияешь так, что блесткам стало стыдно! 💎"
  ],
  sweet: [
    "Ты — самое нежное облачко на небе! ☁️",
    "Твоя доброта согревает даже зимой! 💕",
    "Ты — медовый лунтик среди всех лунтиков! 🍯🌙",
    "Ты пахнешь ванилью и счастьем! 🧁",
    "Ты — самый уютный плед в холодный вечер! 💕",
    "Твои слова — как горячий шоколад в дождливый день! 🍫☕",
    "Ты — сахарная вата, только лучше! 🍭💖",
    "Ты — персик, от которого не хочется оторваться! 🍑✨",
    "Ты — мармеладный мишка, которого все хотят обнять! 🧸💕",
    "Твоя душа — как поле ромашек! 🌼💖",
    "Ты — самый сладкий комплимент, который можно сказать! 💝",
    "Ты — как первое утро весны! ☀️",
    "Ты — клубничка с шоколадом! 🍓🍫",
    "Ты — тёплый свет в окошке! 🏠💖",
    "Ты — мятная свежесть в жаркий день! 🌿"
  ],
  funny: [
    "Ты настолько крут, что даже Wi-Fi ловит лучше рядом с тобой! 😎",
    "Если бы ты был приправой, ты был бы радужной посыпкой! 🌈✨",
    "Ты — тот человек, ради которого кот готов перестать быть высокомерным! 🐱",
    "Ты круче, чем бесплатный Wi-Fi в кафе! 📱",
    "Ты настолько классный, что даже твой холодильник тебя хвалит! 🧊😄",
    "Если бы единороги могли говорить, они бы сказали: 'Хочу быть как ты!' 😂",
    "Ты — как пицца: всегда нужен, всегда любим! 🍕💖",
    "Ты настолько милый, что котёнок на фото покраснел! 🐱😳",
    "Ты — ходячий антистресс! 🧘‍♀️✨",
    "Если бы комплименты были валютой, ты бы уже купил Луну! 🌙",
    "Ты круче, чем найти пятёрку в кармане! 🍀",
    "Ты — как котёнок: милый, но при этом опасный! 🐱😈",
    "Ты настолько хорош, что даже зеркало тебе завидует! 🪞😄",
    "Ты — единственная причина, по которой я нажимаю эту кнопку! 😂💖",
    "Ты — как зарядка на 100% в нужный момент! 🔋⚡"
  ],
  epic: [
    "Ты — легенда! Твоё имя будут вспоминать через тысячелетия! ️👑",
    "Ты — тот герой, о котором слагают баллады! 🎵",
    "Ты настолько мощный, что единороги просят тебя о помощи! 🦄💪",
    "Ты — молния в мире искр! ⚡✨",
    "Ты — тот, кто двигает горы и вдохновляет вселенную! 🌍⚡",
    "Ты — эпический босс, которого все хотят пройти! 🎮👑",
    "Твоя сила духа затмевает сверхновые! 💫⚡",
    "Ты — ходячий эпицентр крутости! 🌪️👑",
    "Ты — тот самый персонаж, за которого все болеют! 🏆",
    "Ты настолько велик, что даже вселенная аплодирует! 🌌👏",
    "Ты — супергерой без плаща, но с единорогом! 🦸‍♂️🦄",
    "Ты — финальный босс, которого никто не может победить! 🎮💪",
    "Ты — стихия, которую невозможно остановить! ⚡",
    "Ты — тот, ради кого стоит свернуть горы! ⛰️👑",
    "Ты — легенда, миф и реальность одновременно! 📜✨"
  ],
  kitten: [
    "Ты — котёнок в мире больших кошек! 🐱💖",
    "Ты такой милый, что котята берут с тебя пример! 🐱👑",
    "Ты — самый пушистый и тёплый человек на планете! 🧶",
    "Ты мурчишь от счастья, и весь мир мурчит вместе с тобой! 🐱",
    "Ты — котик, которого все хотят погладить! 🐱✋",
    "Ты — котёнок с характером единорога! 🐱🦄",
    "Твои лапки — самые милые лапки во вселенной! 🐾💖",
    "Ты — пушистый комочек счастья! 🐱☁️",
    "Ты мурлыкаешь так сладко, что единороги засыпают! 🦄💤",
    "Ты — котёнок, который нашёл свой лучик солнца! 🐱️",
    "Ты — тот котик, который всегда оказывается на коленках! 🐱💕",
    "Ты — розовый котёнок с сердечком на лапках! 🐾💖",
    "Ты мурчишь, и мир становится лучше! 🐱🌍",
    "Ты — котёнок, которого невозможно не любить! 🐱💝",
    "Ты — самый обнимательный котик на свете! 🐱🤗"
  ]
};

let currentMood = 'all';
let praiseCount = 0;
let history = [];
let happinessLevel = 0;
let lastUsedIndex = -1;

function setMood(mood) {
  currentMood = mood;
  document.querySelectorAll('.mood-btn').forEach(btn => {
    btn.classList.toggle('active', btn.dataset.mood === mood);
  });
}

function generatePraise() {
  const pool = praisePhrases[currentMood];
  let idx;
  do {
    idx = Math.floor(Math.random() * pool.length);
  } while (idx === lastUsedIndex && pool.length > 1);
  lastUsedIndex = idx;

  const phrase = pool[idx];
  const praiseText = document.getElementById('praiseText');

  praiseText.classList.add('fade');

  setTimeout(() => {
    praiseText.innerHTML = phrase;
    praiseText.classList.remove('fade');
  }, 300);

  praiseCount++;
  document.getElementById('counterBadge').textContent = praiseCount;

  // Update happiness meter
  happinessLevel = Math.min(5, happinessLevel + 1);
  updateLoveMeter();

  // Add to history
  history.unshift(phrase);
  if (history.length > 20) history.pop();
  updateHistory();

  // Create explosion effect
  createExplosion();

  // Create glitter burst
  createGlitterBurst();

  // Shake the praise box
  const praiseBox = document.getElementById('praiseBox');
  praiseBox.style.animation = 'none';
  praiseBox.offsetHeight;
  praiseBox.style.animation = 'boxShake 0.5s ease';

  // Button pulse
  const btn = document.getElementById('praiseBtn');
  btn.style.transform = 'scale(0.95)';
  setTimeout(() => { btn.style.transform = ''; }, 150);
}

function updateLoveMeter() {
  const hearts = document.querySelectorAll('.love-heart');
  hearts.forEach((heart, i) => {
    if (i < happinessLevel) {
      if (!heart.classList.contains('filled')) {
        heart.classList.add('filled');
        heart.style.animationDelay = (i * 0.1) + 's';
      }
    } else {
      heart.classList.remove('filled');
    }
  });

  // Reset after some time
  clearTimeout(window.resetHappinessTimer);
  window.resetHappinessTimer = setTimeout(() => {
    if (happinessLevel > 0) {
      happinessLevel--;
      updateLoveMeter();
    }
  }, 5000);
}

function updateHistory() {
  const list = document.getElementById('historyList');
  list.innerHTML = history.map((item, i) =>
    `<div class="history-item" style="animation-delay: ${i * 0.05}s">${item}</div>`
  ).join('');
}

function toggleHistory() {
  const list = document.getElementById('historyList');
  const arrow = document.getElementById('historyArrow');
  list.classList.toggle('open');
  arrow.textContent = list.classList.contains('open') ? '▼' : '▶';
}

function createExplosion() {
  const container = document.getElementById('explosionContainer');
  const emojis = ['✨', '💖', '', '🦄', '🐾', '🌈', '💫', '🎀', '🐱', '⭐', '💕', '🌸'];
  const btn = document.getElementById('praiseBtn');
  const rect = btn.getBoundingClientRect();
  const cx = rect.left + rect.width / 2;
  const cy = rect.top + rect.height / 2;

  for (let i = 0; i < 20; i++) {
    const particle = document.createElement('div');
    particle.className = 'burst-particle';
    particle.textContent = emojis[Math.floor(Math.random() * emojis.length)];

    const angle = (Math.PI * 2 * i) / 20;
    const distance = 100 + Math.random() * 150;
    const tx = Math.cos(angle) * distance;
    const ty = Math.sin(angle) * distance;

    particle.style.left = cx + 'px';
    particle.style.top = cy + 'px';
    particle.style.setProperty('--tx', tx + 'px');
    particle.style.setProperty('--ty', ty + 'px');
    particle.style.fontSize = (0.8 + Math.random() * 1.2) + 'em';

    container.appendChild(particle);
    setTimeout(() => particle.remove(), 1200);
  }
}

function createGlitterBurst() {
  const btn = document.getElementById('praiseBtn');
  const rect = btn.getBoundingClientRect();
  const cx = rect.left + rect.width / 2;
  const cy = rect.top + rect.height / 2;

  for (let i = 0; i < 30; i++) {
    const glitter = document.createElement('div');
    glitter.className = 'glitter-burst';

    const angle = Math.random() * Math.PI * 2;
    const dist = 50 + Math.random() * 200;
    const colors = ['#ff6b9d', '#c44dff', '#ffd700', '#ffb6d9', '#ff8ec4', '#fff'];

    glitter.style.left = cx + 'px';
    glitter.style.top = cy + 'px';
    glitter.style.backgroundColor = colors[Math.floor(Math.random() * colors.length)];
    glitter.style.setProperty('--gx', Math.cos(angle) * dist + 'px');
    glitter.style.setProperty('--gy', Math.sin(angle) * dist + 'px');
    glitter.style.width = (3 + Math.random() * 6) + 'px';
    glitter.style.height = glitter.style.width;
    glitter.style.boxShadow = `0 0 ${3 + Math.random() * 5}px ${glitter.style.backgroundColor}`;

    document.body.appendChild(glitter);
    setTimeout(() => glitter.remove(), 800);
  }
}

// Initialize sparkles
function initSparkles() {
  const container = document.getElementById('sparkleContainer');
  const colors = ['', 'gold', 'pink', 'rainbow'];

  for (let i = 0; i < 50; i++) {
    const sparkle = document.createElement('div');
    sparkle.className = 'sparkle ' + colors[Math.floor(Math.random() * colors.length)];
    sparkle.style.left = Math.random() * 100 + '%';
    sparkle.style.top = Math.random() * 100 + '%';
    sparkle.style.setProperty('--dur', (2 + Math.random() * 4) + 's');
    sparkle.style.setProperty('--delay', (Math.random() * 5) + 's');
    sparkle.style.width = (3 + Math.random() * 6) + 'px';
    sparkle.style.height = sparkle.style.width;
    container.appendChild(sparkle);
  }
}

// Initialize floating hearts
function initFloatingHearts() {
  const container = document.getElementById('floatingHearts');
  const hearts = ['💖', '💕', '', '💝', '🌸', '✨', '🦄'];

  for (let i = 0; i < 15; i++) {
    const heart = document.createElement('div');
    heart.className = 'float-heart';
    heart.textContent = hearts[Math.floor(Math.random() * hearts.length)];
    heart.style.left = Math.random() * 100 + '%';
    heart.style.setProperty('--dur', (8 + Math.random() * 12) + 's');
    heart.style.setProperty('--delay', (Math.random() * 10) + 's');
    heart.style.fontSize = (0.8 + Math.random() * 1) + 'em';
    container.appendChild(heart);
  }
}

// Glitter canvas
function initGlitterCanvas() {
  const canvas = document.getElementById('glitterCanvas');
  const ctx = canvas.getContext('2d');

  function resize() {
    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;
  }
  resize();
  window.addEventListener('resize', resize);

  const particles = [];
  for (let i = 0; i < 40; i++) {
    particles.push({
      x: Math.random() * canvas.width,
      y: Math.random() * canvas.height,
      size: Math.random() * 2.5 + 0.5,
      speedX: (Math.random() - 0.5) * 0.3,
      speedY: (Math.random() - 0.5) * 0.3,
      opacity: Math.random(),
      color: ['#ff6b9d', '#c44dff', '#ffd700', '#ffb6d9', '#fff'][Math.floor(Math.random() * 5)]
    });
  }

  function animate() {
    ctx.clearRect(0, 0, canvas.width, canvas.height);

    particles.forEach(p => {
      p.x += p.speedX;
      p.y += p.speedY;
      p.opacity += (Math.random() - 0.5) * 0.05;
      p.opacity = Math.max(0.1, Math.min(0.8, p.opacity));

      if (p.x < 0) p.x = canvas.width;
      if (p.x > canvas.width) p.x = 0;
      if (p.y < 0) p.y = canvas.height;
      if (p.y > canvas.height) p.y = 0;

      ctx.beginPath();
      ctx.arc(p.x, p.y, p.size, 0, Math.PI * 2);
      ctx.fillStyle = p.color;
      ctx.globalAlpha = p.opacity;
      ctx.fill();

      // Star shape
      if (p.size > 1.5) {
        ctx.globalAlpha = p.opacity * 0.5;
        ctx.beginPath();
        ctx.moveTo(p.x - p.size * 2, p.y);
        ctx.lineTo(p.x + p.size * 2, p.y);
        ctx.moveTo(p.x, p.y - p.size * 2);
        ctx.lineTo(p.x, p.y + p.size * 2);
        ctx.strokeStyle = p.color;
        ctx.lineWidth = 0.5;
        ctx.stroke();
      }
    });

    ctx.globalAlpha = 1;
    requestAnimationFrame(animate);
  }

  animate();
}

// Add box shake animation dynamically
const styleSheet = document.createElement('style');
styleSheet.textContent = `
  @keyframes boxShake {
    0%, 100% { transform: translateX(0); }
    10%, 50%, 90% { transform: translateX(-3px); }
    30%, 70% { transform: translateX(3px); }
  }
`;
document.head.appendChild(styleSheet);

// Keyboard shortcut
document.addEventListener('keydown', (e) => {
  if (e.code === 'Space' || e.code === 'Enter') {
    e.preventDefault();
    generatePraise();
  }
});

// Mouse move sparkles
let mouseThrottle = 0;
document.addEventListener('mousemove', (e) => {
  mouseThrottle++;
  if (mouseThrottle % 8 !== 0) return;

  const sparkle = document.createElement('div');
  sparkle.className = 'sparkle pink';
  sparkle.style.left = e.clientX + 'px';
  sparkle.style.top = e.clientY + 'px';
  sparkle.style.width = '4px';
  sparkle.style.height = '4px';
  sparkle.style.setProperty('--dur', '1s');
  sparkle.style.setProperty('--delay', '0s');
  sparkle.style.pointerEvents = 'none';
  sparkle.style.zIndex = '50';
  document.body.appendChild(sparkle);

  setTimeout(() => sparkle.remove(), 1000);
});

// Init
initSparkles();
initFloatingHearts();
initGlitterCanvas();
</script>
</body>
</html>

