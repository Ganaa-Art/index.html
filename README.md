<!DOCTYPE html>
<html lang="mn">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Герман хэл сурцгаая 🇩🇪</title>
<link href="https://fonts.googleapis.com/css2?family=Nunito:wght@400;600;700;800&family=Nunito+Sans:wght@400;600&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --bg: #f0f4ff;
    --card: #ffffff;
    --purple: #6c5ce7;
    --purple-light: #a29bfe;
    --green: #00b894;
    --green-light: #55efc4;
    --red: #d63031;
    --red-light: #fab1a0;
    --yellow: #fdcb6e;
    --text: #2d3436;
    --text-muted: #636e72;
    --shadow: 0 8px 32px rgba(108,92,231,0.10);
    --radius: 18px;
  }

  body {
    font-family: 'Nunito', sans-serif;
    background: var(--bg);
    min-height: 100vh;
    color: var(--text);
    background-image:
      radial-gradient(circle at 20% 20%, #d5ccff 0%, transparent 40%),
      radial-gradient(circle at 80% 80%, #c8f0e8 0%, transparent 40%);
  }

  .container {
    max-width: 560px;
    margin: 0 auto;
    padding: 2rem 1.2rem 3rem;
  }

  /* Header */
  .app-header {
    text-align: center;
    margin-bottom: 1.8rem;
  }
  .app-title {
    font-size: 2rem;
    font-weight: 800;
    color: var(--purple);
    letter-spacing: -0.5px;
  }
  .app-subtitle {
    font-size: 1rem;
    color: var(--text-muted);
    margin-top: 4px;
  }
  .flag { font-size: 1.4rem; }

  /* Score bar */
  .score-bar {
    display: flex;
    justify-content: space-around;
    background: var(--card);
    border-radius: var(--radius);
    padding: 1rem;
    margin-bottom: 1.2rem;
    box-shadow: var(--shadow);
  }
  .score-item { text-align: center; }
  .score-num {
    font-size: 2rem;
    font-weight: 800;
    color: var(--purple);
    line-height: 1;
  }
  .score-label {
    font-size: 0.75rem;
    color: var(--text-muted);
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.04em;
    margin-top: 2px;
  }
  .score-item.streak .score-num { color: #e17055; }
  .score-item.zov .score-num { color: var(--green); }

  /* Tabs */
  .tabs {
    display: flex;
    gap: 8px;
    flex-wrap: wrap;
    margin-bottom: 0.8rem;
  }
  .tab {
    padding: 7px 14px;
    border-radius: 30px;
    border: 2px solid #dfe6e9;
    font-size: 0.85rem;
    font-weight: 700;
    cursor: pointer;
    background: var(--card);
    color: var(--text-muted);
    transition: all 0.15s;
    font-family: 'Nunito', sans-serif;
  }
  .tab:hover { border-color: var(--purple-light); color: var(--purple); }
  .tab.active {
    background: var(--purple);
    border-color: var(--purple);
    color: #fff;
  }

  /* Mode toggle */
  .mode-toggle {
    display: flex;
    gap: 8px;
    margin-bottom: 1.2rem;
  }
  .mode-btn {
    flex: 1;
    padding: 8px 10px;
    border-radius: 30px;
    border: 2px solid #dfe6e9;
    font-size: 0.82rem;
    font-weight: 700;
    cursor: pointer;
    background: var(--card);
    color: var(--text-muted);
    transition: all 0.15s;
    font-family: 'Nunito', sans-serif;
  }
  .mode-btn.active {
    background: #e8f5f1;
    border-color: var(--green);
    color: #00796b;
  }

  /* Progress */
  .progress-wrap {
    background: #dfe6e9;
    border-radius: 8px;
    height: 8px;
    margin-bottom: 1.4rem;
    overflow: hidden;
  }
  .progress-fill {
    height: 100%;
    background: linear-gradient(90deg, var(--purple), var(--purple-light));
    border-radius: 8px;
    transition: width 0.4s cubic-bezier(.4,0,.2,1);
  }

  /* Question card */
  .question-card {
    background: var(--card);
    border-radius: var(--radius);
    padding: 2.2rem 1.5rem 1.8rem;
    text-align: center;
    box-shadow: var(--shadow);
    margin-bottom: 1.2rem;
    position: relative;
    overflow: hidden;
  }
  .question-card::before {
    content: '';
    position: absolute;
    top: -30px; right: -30px;
    width: 100px; height: 100px;
    background: radial-gradient(circle, #d5ccff 0%, transparent 70%);
    border-radius: 50%;
  }
  .q-label {
    font-size: 0.75rem;
    font-weight: 700;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    color: var(--purple-light);
    margin-bottom: 10px;
  }
  .q-word {
    font-size: 2.8rem;
    font-weight: 800;
    color: var(--purple);
    line-height: 1.1;
    word-break: break-word;
  }
  .q-count {
    position: absolute;
    top: 14px; right: 18px;
    font-size: 0.78rem;
    font-weight: 700;
    color: var(--text-muted);
  }

  /* Options grid */
  .options-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 12px;
    margin-bottom: 1rem;
  }
  .opt-btn {
    background: var(--card);
    border: 2.5px solid #dfe6e9;
    border-radius: 14px;
    padding: 16px 10px;
    font-size: 1.05rem;
    font-weight: 700;
    cursor: pointer;
    color: var(--text);
    transition: all 0.15s;
    font-family: 'Nunito', sans-serif;
    box-shadow: 0 2px 8px rgba(0,0,0,0.04);
    position: relative;
    overflow: hidden;
  }
  .opt-btn:hover:not(:disabled) {
    border-color: var(--purple-light);
    color: var(--purple);
    transform: translateY(-2px);
    box-shadow: 0 6px 18px rgba(108,92,231,0.12);
  }
  .opt-btn.correct {
    background: #e8f5f1;
    border-color: var(--green);
    color: #00796b;
  }
  .opt-btn.wrong {
    background: #fff0ee;
    border-color: var(--red);
    color: var(--red);
  }
  .opt-btn:disabled { cursor: default; transform: none; }

  /* Feedback */
  .feedback {
    text-align: center;
    font-size: 1.05rem;
    font-weight: 700;
    min-height: 30px;
    margin-bottom: 0.5rem;
  }
  .feedback.correct { color: var(--green); }
  .feedback.wrong { color: var(--red); }

  /* Next button */
  .next-btn {
    display: block;
    width: 100%;
    padding: 14px;
    border-radius: 14px;
    border: none;
    background: var(--purple);
    color: #fff;
    font-size: 1rem;
    font-weight: 800;
    cursor: pointer;
    font-family: 'Nunito', sans-serif;
    box-shadow: 0 4px 18px rgba(108,92,231,0.25);
    transition: all 0.15s;
    margin-top: 8px;
  }
  .next-btn:hover { background: #5a4bd1; transform: translateY(-1px); }
  .next-btn:active { transform: scale(0.98); }

  /* Result screen */
  .result-screen {
    background: var(--card);
    border-radius: var(--radius);
    padding: 2.5rem 1.5rem;
    text-align: center;
    box-shadow: var(--shadow);
  }
  .result-emoji { font-size: 4rem; margin-bottom: 1rem; }
  .result-pct {
    font-size: 3.5rem;
    font-weight: 800;
    color: var(--purple);
    line-height: 1;
  }
  .result-msg {
    font-size: 1.1rem;
    font-weight: 700;
    color: var(--text);
    margin: 10px 0 6px;
  }
  .result-sub {
    font-size: 0.95rem;
    color: var(--text-muted);
    margin-bottom: 1.6rem;
  }
  .restart-btn {
    padding: 14px 40px;
    border-radius: 14px;
    border: none;
    background: var(--purple);
    color: #fff;
    font-size: 1rem;
    font-weight: 800;
    cursor: pointer;
    font-family: 'Nunito', sans-serif;
    box-shadow: 0 4px 18px rgba(108,92,231,0.25);
    transition: all 0.15s;
  }
  .restart-btn:hover { background: #5a4bd1; }

  /* Confetti particle */
  @keyframes pop-in {
    0% { transform: scale(0.7); opacity: 0; }
    60% { transform: scale(1.08); }
    100% { transform: scale(1); opacity: 1; }
  }
  .question-card { animation: pop-in 0.25s ease; }

  /* Responsive */
  @media (max-width: 400px) {
    .q-word { font-size: 2.2rem; }
    .opt-btn { font-size: 0.95rem; padding: 13px 8px; }
    .app-title { font-size: 1.6rem; }
  }
</style>
</head>
<body>
<div class="container">

  <div class="app-header">
    <div class="app-title"><span class="flag">🇩🇪</span> Герман хэл <span class="flag">🇲🇳</span></div>
    <div class="app-subtitle">Тоглоомоор хэл сурцгаая!</div>
  </div>

  <div class="score-bar">
    <div class="score-item zov">
      <div class="score-num" id="sc-correct">0</div>
      <div class="score-label">Зөв</div>
    </div>
    <div class="score-item">
      <div class="score-num" id="sc-total">0</div>
      <div class="score-label">Нийт</div>
    </div>
    <div class="score-item streak">
      <div class="score-num" id="sc-streak">0</div>
      <div class="score-label">🔥 Дараалал</div>
    </div>
  </div>

  <div class="tabs" id="tabs">
    <button class="tab active" data-cat="all">🌟 Бүгд</button>
    <button class="tab" data-cat="colors">🎨 Өнгө</button>
    <button class="tab" data-cat="numbers">🔢 Тоо</button>
    <button class="tab" data-cat="days">📅 Өдрүүд</button>
    <button class="tab" data-cat="greetings">👋 Мэндчилгээ</button>
    <button class="tab" data-cat="family">👨‍👩‍👧 Гэр бүл</button>
    <button class="tab" data-cat="body">🧍 Бие</button>
    <button class="tab" data-cat="food">🍎 Хоол</button>
  </div>

  <div class="mode-toggle">
    <button class="mode-btn active" data-mode="de-mn">🇩🇪 → 🇲🇳 Герман → Монгол</button>
    <button class="mode-btn" data-mode="mn-de">🇲🇳 → 🇩🇪 Монгол → Герман</button>
  </div>

  <div class="progress-wrap">
    <div class="progress-fill" id="prog" style="width:0%"></div>
  </div>

  <div id="game-area"></div>

</div>

<script>
const WORDS = {
  colors: [
    {de:"rot",mn:"улаан"},{de:"blau",mn:"цэнхэр"},{de:"grün",mn:"ногоон"},
    {de:"gelb",mn:"шар"},{de:"weiß",mn:"цагаан"},{de:"schwarz",mn:"хар"},
    {de:"orange",mn:"улбар шар"},{de:"lila",mn:"нил ягаан"},{de:"rosa",mn:"ягаан"},
    {de:"braun",mn:"хүрэн"}
  ],
  numbers: [
    {de:"eins",mn:"нэг"},{de:"zwei",mn:"хоёр"},{de:"drei",mn:"гурав"},
    {de:"vier",mn:"дөрөв"},{de:"fünf",mn:"тав"},{de:"sechs",mn:"зургаа"},
    {de:"sieben",mn:"долоо"},{de:"acht",mn:"найм"},{de:"neun",mn:"ес"},
    {de:"zehn",mn:"арав"},{de:"null",mn:"тэг"},{de:"zwanzig",mn:"хорь"}
  ],
  days: [
    {de:"Montag",mn:"Даваа"},{de:"Dienstag",mn:"Мягмар"},{de:"Mittwoch",mn:"Лхагва"},
    {de:"Donnerstag",mn:"Пүрэв"},{de:"Freitag",mn:"Баасан"},
    {de:"Samstag",mn:"Бямба"},{de:"Sonntag",mn:"Ням"}
  ],
  greetings: [
    {de:"Hallo",mn:"Сайн уу"},{de:"Guten Morgen",mn:"Өглөөний мэнд"},
    {de:"Guten Tag",mn:"Өдрийн мэнд"},{de:"Guten Abend",mn:"Оройн мэнд"},
    {de:"Auf Wiedersehen",mn:"Баяртай"},{de:"Tschüss",mn:"Бяртай (дотно)"},
    {de:"Danke",mn:"Баярлалаа"},{de:"Bitte",mn:"Гуйя / Зүгээр"},
    {de:"Entschuldigung",mn:"Уучлаарай"},{de:"Ja",mn:"Тийм"},{de:"Nein",mn:"Үгүй"}
  ],
  family: [
    {de:"Mutter",mn:"Ээж"},{de:"Vater",mn:"Аав"},{de:"Kind",mn:"Хүүхэд"},
    {de:"Bruder",mn:"Ах / Дүү (эрэгтэй)"},{de:"Schwester",mn:"Эгч / Дүү (эмэгтэй)"},
    {de:"Oma",mn:"Эмээ"},{de:"Opa",mn:"Өвөө"},{de:"Baby",mn:"Нярай"}
  ],
  body: [
    {de:"Kopf",mn:"Толгой"},{de:"Hand",mn:"Гар"},{de:"Fuß",mn:"Хөл"},
    {de:"Auge",mn:"Нүд"},{de:"Nase",mn:"Хамар"},{de:"Mund",mn:"Ам"},
    {de:"Ohr",mn:"Чих"},{de:"Bauch",mn:"Гэдэс"}
  ],
  food: [
    {de:"Apfel",mn:"Алим"},{de:"Brot",mn:"Талх"},{de:"Milch",mn:"Сүү"},
    {de:"Wasser",mn:"Ус"},{de:"Ei",mn:"Өндөг"},{de:"Käse",mn:"Бяслаг"},
    {de:"Banane",mn:"Гадил"},{de:"Fleisch",mn:"Мах"},{de:"Suppe",mn:"Шөл"}
  ]
};

const MAX_Q = 15;
let state = {
  cat:'all', mode:'de-mn',
  correct:0, total:0, streak:0, asked:0, answered:false
};

function getPool() {
  return state.cat === 'all' ? Object.values(WORDS).flat() : (WORDS[state.cat] || []);
}
function shuffle(a) {
  const b = [...a];
  for(let i=b.length-1;i>0;i--){const j=Math.floor(Math.random()*(i+1));[b[i],b[j]]=[b[j],b[i]];}
  return b;
}
function resetScore() {
  state.correct=0;state.total=0;state.streak=0;state.asked=0;
  document.getElementById('sc-correct').textContent=0;
  document.getElementById('sc-total').textContent=0;
  document.getElementById('sc-streak').textContent=0;
}

function render() {
  const area = document.getElementById('game-area');
  document.getElementById('prog').style.width = Math.round(state.asked/MAX_Q*100)+'%';

  if(state.asked >= MAX_Q) { renderResult(area); return; }

  const pool = getPool();
  if(pool.length < 4) {
    area.innerHTML = '<p style="text-align:center;color:#636e72;padding:2rem">Энэ ангилалд үг хангалтгүй байна.</p>';
    return;
  }
  const sh = shuffle(pool);
  const correct = sh[0];
  const opts = shuffle([correct, ...sh.slice(1,4)]);
  state.answered = false;

  const qText = state.mode==='de-mn' ? correct.de : correct.mn;
  const qLabel = state.mode==='de-mn' ? '🇩🇪 Герман үг' : '🇲🇳 Монгол үг';
  const qNum = state.asked+1;

  area.innerHTML = `
    <div class="question-card">
      <div class="q-count">${qNum} / ${MAX_Q}</div>
      <div class="q-label">${qLabel}</div>
      <div class="q-word">${qText}</div>
    </div>
    <div class="options-grid" id="opts"></div>
    <div class="feedback" id="fb"></div>
    <button class="next-btn" id="nxt" style="display:none">Дараах ➜</button>
  `;

  const optsEl = document.getElementById('opts');
  opts.forEach(opt => {
    const btn = document.createElement('button');
    btn.className = 'opt-btn';
    btn.textContent = state.mode==='de-mn' ? opt.mn : opt.de;
    btn.dataset.de = opt.de;
    btn.onclick = () => check(btn, opt, correct);
    optsEl.appendChild(btn);
  });

  document.getElementById('nxt').onclick = () => { state.asked++; render(); };
}

function check(btn, chosen, correct) {
  if(state.answered) return;
  state.answered = true;
  state.total++;
  document.getElementById('sc-total').textContent = state.total;

  const ok = chosen.de === correct.de;
  document.querySelectorAll('.opt-btn').forEach(b => {
    b.disabled = true;
    if(b.dataset.de === correct.de) b.classList.add('correct');
    else if(b===btn && !ok) b.classList.add('wrong');
  });

  const fb = document.getElementById('fb');
  if(ok) {
    state.correct++; state.streak++;
    document.getElementById('sc-correct').textContent = state.correct;
    document.getElementById('sc-streak').textContent = state.streak;
    const msgs = ['🎉 Маш сайн!','✅ Зөв!','⭐ Гайхалтай!','🌟 Тэгж байгаа!','🔥 Үлгэрлэсэн!'];
    fb.textContent = msgs[Math.floor(Math.random()*msgs.length)];
    fb.className = 'feedback correct';
  } else {
    state.streak=0;
    document.getElementById('sc-streak').textContent=0;
    const ans = state.mode==='de-mn' ? correct.mn : correct.de;
    fb.textContent = `❌ Зөв хариулт: ${ans}`;
    fb.className = 'feedback wrong';
  }
  document.getElementById('nxt').style.display='block';
}

function renderResult(area) {
  const pct = state.total ? Math.round(state.correct/state.total*100) : 0;
  let emoji='😊', msg='Дахин оролдоорой!', sub='Та дахин тоглоход илүү сайн болно.';
  if(pct>=90){emoji='🌟';msg='Гайхалтай! Та маш сайн!';sub='Та германы хэлний мэргэжилтэн болж байна!';}
  else if(pct>=70){emoji='😄';msg='Сайн байна!';sub='Үргэлжлүүлэн дадлага хий!';}
  else if(pct>=50){emoji='🙂';msg='Дунд зэрэг.';sub='Давтаж байгаарай, чадна!';}
  else{emoji='💪';msg='Бодит оролдлого!';sub='Дахин оролдоход заавал ахиц байна.';}

  area.innerHTML = `
    <div class="result-screen">
      <div class="result-emoji">${emoji}</div>
      <div class="result-pct">${pct}%</div>
      <div class="result-msg">${msg}</div>
      <div class="result-sub">${state.correct} / ${state.total} зөв — ${sub}</div>
      <button class="restart-btn" id="restart">🔄 Дахин тоглох</button>
    </div>
  `;
  document.getElementById('restart').onclick = () => { resetScore(); render(); };
}

// Tab events
document.getElementById('tabs').addEventListener('click', e => {
  const t = e.target.closest('.tab'); if(!t) return;
  document.querySelectorAll('.tab').forEach(x=>x.classList.remove('active'));
  t.classList.add('active');
  state.cat = t.dataset.cat;
  resetScore(); render();
});

// Mode events
document.querySelectorAll('.mode-btn').forEach(b => {
  b.onclick = () => {
    document.querySelectorAll('.mode-btn').forEach(x=>x.classList.remove('active'));
    b.classList.add('active');
    state.mode = b.dataset.mode;
    state.asked=0; render();
  };
});

render();
</script>
</body>
</html>
