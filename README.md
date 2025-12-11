[work11.html](https://github.com/user-attachments/files/24102694/work11.html)<!doctype html>
<html lang="uk">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Анімація marquee та CSS</title>

  <link rel="stylesheet" href="marquee_styles.css">
</head>
<body>

  <h1>Анімація: тег &lt;marquee&gt; та CSS @keyframes</h1>

  <div class="card">
    <h2>Класичний тег &lt;marquee&gt;</h2>

    <marquee behavior="scroll" direction="left" scrollamount="6">
      Це приклад руху тексту вліво за допомогою тегу marquee.
    </marquee>

    <pre>
&lt;marquee behavior="alternate" direction="right" scrollamount="4"&gt;
  Рух туди-сюди
&lt;/marquee&gt;
    </pre>
  </div>

  <div class="card">
    <h2>CSS-анімація: горизонтальний ticker</h2>

    <div class="ticker-wrap">
      <div class="ticker">
        <span class="item">Новина 1 — текст</span>
        <span class="item">Новина 2 — оновлення</span>
        <span class="item">Акція — знижка 20%</span>

        <span class="item">Новина 1 — текст</span>
        <span class="item">Новина 2 — оновлення</span>
        <span class="item">Акція — знижка 20%</span>
      </div>
    </div>
  </div>

  <div class="card">
    <h2>CSS вертикальна анімація</h2>

    <div class="vertical-wrap">
      <ul class="vertical-list">
        <li>Повідомлення №1</li>
        <li>Повідомлення №2</li>
        <li>Повідомлення №3</li>

        <li>Повідомлення №1</li>
        <li>Повідомлення №2</li>
        <li>Повідомлення №3</li>
      </ul>
    </div>
  </div>

  <div class="card">
    <h2>CSS Bounce-анімація</h2>

    <div class="bounce" style="white-space:nowrap;">
      <div class="text">
        ⬅️➡️ Текст рухається туди-сюди, імітуючи відскок
      </div>
    </div>
  </div>

</body>
</html>

[stlyle.css](https://github.com/user-attachments/files/24102715/stlyle.css)

body {
  font-family: system-ui, -apple-system, 'Segoe UI', Roboto, Arial;
  line-height: 1.5;
  padding: 2rem;
  background: #f7f7fb;
  color: #111;
}

h1, h2 { margin: .5rem 0 1rem; }

.card {
  background: #fff;
  border-radius: 12px;
  padding: 1rem 1.25rem;
  box-shadow: 0 6px 18px rgba(20,20,40,.06);
  margin-bottom: 1.25rem;
}

pre {
  background: #0b1220;
  color: #cfe9ff;
  padding: 1rem;
  border-radius: 8px;
  overflow: auto;
}

.ticker-wrap {
  overflow: hidden;
  position: relative;
}

.ticker {
  display: inline-block;
  white-space: nowrap;
  will-change: transform;
  animation: ticker 12s linear infinite;
}

@keyframes ticker {
  from { transform: translateX(0%); }
  to { transform: translateX(-50%); }
}

.ticker .item {
  display: inline-block;
  padding: 0 .75rem;
  font-weight: 600;
}

.ticker-wrap:hover .ticker {
  animation-play-state: paused;
}

.vertical-wrap {
  height: 3.2rem;
  overflow: hidden;
}

.vertical-list {
  display: block;
  animation: vertical 6s linear infinite;
}

@keyframes vertical {
  0% { transform: translateY(0%); }
  25% { transform: translateY(-33.333%); }
  50% { transform: translateY(-66.666%); }
  75% { transform: translateY(-100%); }
  100% { transform: translateY(0%); }
}

.vertical-list li {
  list-style: none;
  padding: .4rem 0;
}

.bounce { overflow: hidden; }

.bounce .text {
  display: inline-block;
  animation: bounce 4s ease-in-out infinite;
}

@keyframes bounce {
  0% { transform: translateX(0); }
  50% { transform: translateX(calc(100% - 100vw)); }
  100% { transform: translateX(0); }
}

.muted { color: #666; font-size: .95rem; }

code {
  background: #eef2ff;
  padding: .15rem .35rem;
  border-radius: .25rem;
}
