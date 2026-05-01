<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>부쟈의 프로필 ♡</title>
<link href="https://fonts.googleapis.com/css2?family=Noto+Sans+KR:wght@300;400;500;700&family=Playfair+Display:ital@0;1&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --cream: #FFF8EE;
    --butter: #F5E6C8;
    --soft-yellow: #F9EFA3;
    --warm-pink: #F2A7B3;
    --blush: #F7D1D8;
    --lilac: #D9C5F0;
    --mint: #C5E8D9;
    --text-dark: #3a2e2e;
    --text-mid: #7a6060;
    --accent: #e88fa0;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background-color: var(--cream);
    background-image:
      radial-gradient(circle at 10% 20%, rgba(242,167,179,0.15) 0%, transparent 40%),
      radial-gradient(circle at 90% 80%, rgba(217,197,240,0.2) 0%, transparent 40%),
      radial-gradient(circle at 50% 50%, rgba(249,239,163,0.1) 0%, transparent 60%);
    font-family: 'Noto Sans KR', sans-serif;
    min-height: 100vh;
    overflow-x: hidden;
    cursor: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='20' height='20' viewBox='0 0 20 20'%3E%3Ccircle cx='10' cy='10' r='8' fill='%23F2A7B3' opacity='0.7'/%3E%3C/svg%3E"), auto;
  }

  /* Floating deco elements */
  .deco-bg {
    position: fixed;
    pointer-events: none;
    z-index: 0;
    width: 100%;
    height: 100%;
    top: 0; left: 0;
    overflow: hidden;
  }

  .bubble {
    position: absolute;
    border-radius: 50%;
    animation: floatBubble linear infinite;
    opacity: 0.18;
  }

  @keyframes floatBubble {
    0% { transform: translateY(110vh) scale(0.8); opacity: 0; }
    10% { opacity: 0.18; }
    90% { opacity: 0.18; }
    100% { transform: translateY(-10vh) scale(1.1); opacity: 0; }
  }

  .star-deco {
    position: fixed;
    font-size: 14px;
    animation: twinkle 3s ease-in-out infinite;
    pointer-events: none;
    z-index: 0;
  }

  @keyframes twinkle {
    0%, 100% { opacity: 0.3; transform: scale(1) rotate(0deg); }
    50% { opacity: 1; transform: scale(1.3) rotate(15deg); }
  }

  /* Main layout */
  .wrapper {
    position: relative;
    z-index: 1;
    max-width: 600px;
    margin: 0 auto;
    padding: 40px 20px 80px;
  }

  /* Header */
  .site-header {
    text-align: center;
    margin-bottom: 32px;
    animation: fadeDown 0.8s ease forwards;
  }

  @keyframes fadeDown {
    from { opacity: 0; transform: translateY(-20px); }
    to { opacity: 1; transform: translateY(0); }
  }

  .marquee-wrap {
    overflow: hidden;
    background: linear-gradient(90deg, var(--warm-pink), var(--lilac), var(--soft-yellow), var(--mint), var(--warm-pink));
    background-size: 300% 100%;
    animation: gradShift 4s ease infinite;
    border-radius: 30px;
    padding: 6px 0;
    margin-bottom: 20px;
  }

  @keyframes gradShift {
    0% { background-position: 0% 50%; }
    50% { background-position: 100% 50%; }
    100% { background-position: 0% 50%; }
  }

  .marquee-text {
    display: inline-block;
    white-space: nowrap;
    animation: marqueeScroll 18s linear infinite;
    font-size: 12px;
    font-weight: 500;
    color: white;
    letter-spacing: 2px;
  }

  @keyframes marqueeScroll {
    from { transform: translateX(0); }
    to { transform: translateX(-50%); }
  }

  .site-title {
    font-family: 'Playfair Display', serif;
    font-size: 13px;
    font-style: italic;
    color: var(--text-mid);
    letter-spacing: 4px;
    text-transform: uppercase;
  }

  /* Photo card */
  .photo-section {
    display: flex;
    justify-content: center;
    margin-bottom: 28px;
    animation: fadeUp 0.9s 0.2s ease both;
  }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(24px); }
    to { opacity: 1; transform: translateY(0); }
  }

  .photo-frame {
    position: relative;
    display: inline-block;
  }

  .photo-frame::before {
    content: '';
    position: absolute;
    inset: -8px;
    border-radius: 24px;
    background: linear-gradient(135deg, var(--warm-pink), var(--lilac), var(--soft-yellow));
    z-index: -1;
    animation: rotateBorder 6s linear infinite;
  }

  @keyframes rotateBorder {
    from { filter: hue-rotate(0deg); }
    to { filter: hue-rotate(360deg); }
  }

  .photo-frame img {
    width: 260px;
    height: 260px;
    object-fit: cover;
    border-radius: 20px;
    display: block;
    border: 4px solid white;
  }

  .photo-badge {
    position: absolute;
    background: white;
    border-radius: 20px;
    padding: 4px 10px;
    font-size: 11px;
    font-weight: 700;
    box-shadow: 0 2px 12px rgba(0,0,0,0.1);
    animation: popIn 0.5s cubic-bezier(0.34,1.56,0.64,1) both;
  }

  @keyframes popIn {
    from { opacity: 0; transform: scale(0); }
    to { opacity: 1; transform: scale(1); }
  }

  .badge-top {
    top: -12px; right: -12px;
    color: var(--accent);
    animation-delay: 0.8s;
  }

  .badge-bottom {
    bottom: -12px; left: -12px;
    color: #9b7ed4;
    animation-delay: 1s;
  }

  /* Name section */
  .name-section {
    text-align: center;
    margin-bottom: 28px;
    animation: fadeUp 0.9s 0.35s ease both;
  }

  .name-tag {
    display: inline-block;
    font-family: 'Playfair Display', serif;
    font-size: 38px;
    font-weight: 700;
    color: var(--text-dark);
    position: relative;
  }

  .name-tag::after {
    content: '';
    position: absolute;
    bottom: 0; left: 0; right: 0;
    height: 8px;
    background: linear-gradient(90deg, var(--warm-pink), var(--lilac));
    border-radius: 4px;
    opacity: 0.5;
    z-index: -1;
    transform: translateY(-2px);
  }

  .name-sub {
    margin-top: 6px;
    font-size: 12px;
    color: var(--text-mid);
    letter-spacing: 3px;
  }

  /* Info cards */
  .cards-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 12px;
    margin-bottom: 16px;
    animation: fadeUp 0.9s 0.5s ease both;
  }

  .card {
    background: white;
    border-radius: 18px;
    padding: 16px;
    box-shadow: 0 2px 16px rgba(200,160,180,0.12);
    border: 1.5px solid rgba(242,167,179,0.2);
    transition: transform 0.25s ease, box-shadow 0.25s ease;
    position: relative;
    overflow: hidden;
  }

  .card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 3px;
    background: linear-gradient(90deg, var(--warm-pink), var(--lilac));
    border-radius: 18px 18px 0 0;
  }

  .card:hover {
    transform: translateY(-4px);
    box-shadow: 0 8px 24px rgba(200,160,180,0.2);
  }

  .card.full {
    grid-column: 1 / -1;
  }

  .card-emoji {
    font-size: 22px;
    margin-bottom: 6px;
    display: block;
  }

  .card-label {
    font-size: 10px;
    font-weight: 700;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 4px;
  }

  .card-value {
    font-size: 14px;
    color: var(--text-dark);
    font-weight: 500;
    line-height: 1.6;
  }

  .tag {
    display: inline-block;
    padding: 3px 10px;
    border-radius: 20px;
    font-size: 12px;
    font-weight: 500;
    margin: 2px 2px 0 0;
  }

  .tag-pink { background: var(--blush); color: #c0687a; }
  .tag-purple { background: var(--lilac); color: #7b52b8; }
  .tag-yellow { background: var(--soft-yellow); color: #a08530; }
  .tag-mint { background: var(--mint); color: #3a8a68; }

  /* Activity bar */
  .activity-section {
    animation: fadeUp 0.9s 0.65s ease both;
    margin-bottom: 16px;
  }

  .activity-bars {
    display: flex;
    flex-direction: column;
    gap: 8px;
  }

  .bar-row {
    display: flex;
    align-items: center;
    gap: 10px;
    background: white;
    border-radius: 14px;
    padding: 10px 14px;
    border: 1.5px solid rgba(242,167,179,0.15);
    box-shadow: 0 2px 10px rgba(200,160,180,0.08);
  }

  .bar-label {
    font-size: 12px;
    color: var(--text-mid);
    width: 80px;
    flex-shrink: 0;
  }

  .bar-track {
    flex: 1;
    height: 8px;
    background: var(--butter);
    border-radius: 10px;
    overflow: hidden;
  }

  .bar-fill {
    height: 100%;
    border-radius: 10px;
    animation: growBar 1.2s cubic-bezier(0.34,1.1,0.64,1) both;
  }

  @keyframes growBar {
    from { width: 0 !important; }
  }

  .bar-fill.pink { background: linear-gradient(90deg, var(--warm-pink), #f4c0ca); animation-delay: 0.8s; }
  .bar-fill.purple { background: linear-gradient(90deg, var(--lilac), #c4aaee); animation-delay: 0.95s; }
  .bar-fill.yellow { background: linear-gradient(90deg, #f0d060, #f5e68a); animation-delay: 1.1s; }

  .bar-pct {
    font-size: 11px;
    font-weight: 700;
    color: var(--accent);
    width: 32px;
    text-align: right;
  }

  /* Footer card */
  .footer-card {
    animation: fadeUp 0.9s 0.8s ease both;
    text-align: center;
    background: white;
    border-radius: 18px;
    padding: 16px;
    box-shadow: 0 2px 16px rgba(200,160,180,0.12);
    border: 1.5px solid rgba(242,167,179,0.2);
    margin-bottom: 16px;
  }

  .footer-card p {
    font-size: 12px;
    color: var(--text-mid);
    line-height: 2;
  }

  .footer-card strong {
    color: var(--accent);
    font-weight: 600;
  }

  /* Bottom stamp */
  .stamp {
    text-align: center;
    animation: fadeUp 0.9s 0.95s ease both;
  }

  .stamp-inner {
    display: inline-block;
    border: 2px dashed rgba(242,167,179,0.5);
    border-radius: 50px;
    padding: 8px 24px;
    font-size: 11px;
    color: var(--text-mid);
    letter-spacing: 2px;
  }

  /* Floating hearts */
  .heart-float {
    position: fixed;
    font-size: 16px;
    pointer-events: none;
    z-index: 999;
    animation: heartRise 2s ease forwards;
    opacity: 0;
  }

  @keyframes heartRise {
    0% { opacity: 1; transform: translateY(0) scale(1); }
    100% { opacity: 0; transform: translateY(-80px) scale(0.5); }
  }
</style>
</head>
<body>

<!-- Deco background bubbles -->
<div class="deco-bg" id="decoBg"></div>

<!-- Stars -->
<div class="star-deco" style="top:8%;left:5%;animation-delay:0s">✦</div>
<div class="star-deco" style="top:15%;right:8%;animation-delay:1s;color:var(--lilac)">✧</div>
<div class="star-deco" style="top:40%;left:3%;animation-delay:2s;color:var(--warm-pink)">✦</div>
<div class="star-deco" style="top:60%;right:5%;animation-delay:0.5s;color:var(--soft-yellow)">✦</div>
<div class="star-deco" style="bottom:20%;left:7%;animation-delay:1.5s">✧</div>
<div class="star-deco" style="bottom:10%;right:6%;animation-delay:2.5s;color:var(--mint)">✦</div>

<div class="wrapper">

  <!-- Header marquee -->
  <header class="site-header">
    <div class="marquee-wrap">
      <span class="marquee-text">
        ♡ 부쟈의 프로필 &nbsp;·&nbsp; welcome to my page &nbsp;·&nbsp; ☆ bl gl hl 다먹음 ☆ &nbsp;·&nbsp; 마누라 앓이 전문 &nbsp;·&nbsp; ♡ 부쟈의 프로필 &nbsp;·&nbsp; welcome to my page &nbsp;·&nbsp; ☆ bl gl hl 다먹음 ☆ &nbsp;·&nbsp; 마누라 앓이 전문 &nbsp;·&nbsp;
      </span>
    </div>
    <p class="site-title">꽃길만 걸어요 ✦ profile</p>
  </header>

  <!-- Photo -->
  <div class="photo-section">
    <div class="photo-frame">
      <img src="https://raw.githubusercontent.com/dys1537-netizen/obj/refs/heads/main/from-PixAI-2006824781371567093-1.png" alt="부쟈 프로필" />
      <span class="photo-badge badge-top">♡ 부쟈</span>
      <span class="photo-badge badge-bottom">성인 ✦</span>
    </div>
  </div>

  <!-- Name -->
  <div class="name-section">
    <div class="name-tag">부쟈</div>
    <p class="name-sub">성인 &nbsp;·&nbsp; 블언블 &nbsp;·&nbsp; 마누라 앓이 95%</p>
  </div>

  <!-- Info cards grid -->
  <div class="cards-grid">

    <div class="card">
      <span class="card-emoji">🌸</span>
      <div class="card-label">Platform</div>
      <div class="card-value">
        <span class="tag tag-pink">팅글</span>
        <span class="tag tag-purple">블룸</span>
        <span class="tag tag-yellow">로판</span>
      </div>
    </div>

    <div class="card">
      <span class="card-emoji">🐻</span>
      <div class="card-label">트윗 성향</div>
      <div class="card-value">
        <span class="tag tag-pink">맘찍</span>
        <span class="tag tag-purple">일상</span>
        <span class="tag tag-mint">앓이</span>
      </div>
    </div>

    <div class="card">
      <span class="card-emoji">📚</span>
      <div class="card-label">선호 장르</div>
      <div class="card-value">다 먹음 🍰</div>
    </div>

    <div class="card">
      <span class="card-emoji">💕</span>
      <div class="card-label">커플링</div>
      <div class="card-value">
        <span class="tag tag-purple">BL</span>
        <span class="tag tag-pink">GL</span>
        <span class="tag tag-mint">HL</span>
        <br>
        <span style="font-size:11px;color:var(--text-mid)">다 먹음 ♡</span>
      </div>
    </div>

    <div class="card full">
      <span class="card-emoji">🚫</span>
      <div class="card-label">NG</div>
      <div class="card-value">알아서 피함 👀</div>
    </div>

  </div>

  <!-- Activity bars -->
  <div class="activity-section">
    <div class="card" style="margin-bottom:0;border-radius:18px;">
      <span class="card-emoji">🎯</span>
      <div class="card-label" style="margin-bottom:12px;">활동 성향</div>
      <div class="activity-bars">
        <div class="bar-row">
          <span class="bar-label">마누라 앓이</span>
          <div class="bar-track">
            <div class="bar-fill pink" style="width:95%"></div>
          </div>
          <span class="bar-pct">95%</span>
        </div>
        <div class="bar-row">
          <span class="bar-label">소비</span>
          <div class="bar-track">
            <div class="bar-fill purple" style="width:40%"></div>
          </div>
          <span class="bar-pct">4%</span>
        </div>
        <div class="bar-row">
          <span class="bar-label">제작</span>
          <div class="bar-track">
            <div class="bar-fill yellow" style="width:10%"></div>
          </div>
          <span class="bar-pct">1%</span>
        </div>
      </div>
    </div>
  </div>

  <!-- Footer info -->
  <div class="footer-card">
    <p>
      헤어질 때는 <strong>블언블</strong> 💌<br>
      NG는 <strong>알아서 피함</strong> 🌙<br>
      마누라 앓이 계정입니다 ♡
    </p>
  </div>

  <!-- Stamp -->
  <div class="stamp">
    <div class="stamp-inner">✦ 부쟈 · since 성인 · 꽃길만 ✦</div>
  </div>

</div>

<script>
  // Floating bubbles background
  const bg = document.getElementById('decoBg');
  const colors = ['#F2A7B3','#D9C5F0','#F9EFA3','#C5E8D9','#F7D1D8'];
  for (let i = 0; i < 12; i++) {
    const b = document.createElement('div');
    b.className = 'bubble';
    const size = 30 + Math.random() * 60;
    b.style.cssText = `
      width:${size}px;height:${size}px;
      left:${Math.random()*100}%;
      background:${colors[Math.floor(Math.random()*colors.length)]};
      animation-duration:${12+Math.random()*16}s;
      animation-delay:${Math.random()*10}s;
    `;
    bg.appendChild(b);
  }

  // Click heart effect
  document.body.addEventListener('click', (e) => {
    const hearts = ['♡','♥','˚✧','✦','☆'];
    const h = document.createElement('div');
    h.className = 'heart-float';
    h.textContent = hearts[Math.floor(Math.random()*hearts.length)];
    h.style.left = e.clientX + 'px';
    h.style.top = e.clientY + 'px';
    h.style.color = ['#F2A7B3','#D9C5F0','#f0d060','#a5d8c0'][Math.floor(Math.random()*4)];
    document.body.appendChild(h);
    setTimeout(() => h.remove(), 2000);
  });
</script>
</body>
</html>
