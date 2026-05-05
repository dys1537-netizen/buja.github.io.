
<html lang="ko">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>부쟈의 프로필 ♡</title>
<link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display:ital@0;1&family=Noto+Sans+KR:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #FDFAF4;
    --butter: #F5E9C8;
    --butter-dark: #E8D4A0;
    --cream: #FFF8EE;
    --text: #2C2420;
    --text-soft: #9A8A7A;
    --line: rgba(200,170,130,0.25);
    --yellow: #F0D060;
    --pink: #F2B8C0;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    font-family: 'Noto Sans KR', sans-serif;
    font-weight: 300;
    color: var(--text);
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* subtle noise texture overlay */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.03'/%3E%3C/svg%3E");
    pointer-events: none;
    z-index: 0;
    opacity: 0.4;
  }

  .page {
    position: relative;
    z-index: 1;
    max-width: 480px;
    margin: 0 auto;
    padding: 60px 28px 80px;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 0;
  }

  /* ── ticker ── */
  .ticker {
    width: 100%;
    overflow: hidden;
    margin-bottom: 52px;
    opacity: 0;
    animation: fadeIn 0.6s 0.1s forwards;
  }

  .ticker-inner {
    display: flex;
    white-space: nowrap;
    animation: scroll 22s linear infinite;
    gap: 0;
  }

  .ticker-text {
    font-size: 10px;
    letter-spacing: 3px;
    color: var(--text-soft);
    text-transform: uppercase;
    padding-right: 60px;
    flex-shrink: 0;
  }

  @keyframes scroll { from { transform: translateX(0); } to { transform: translateX(-50%); } }

  /* ── photo ── */
  .photo-wrap {
    position: relative;
    margin-bottom: 36px;
    opacity: 0;
    animation: riseUp 0.8s 0.2s cubic-bezier(0.22,1,0.36,1) forwards;
  }

  .photo-deco {
    position: absolute;
    width: 200px;
    height: 200px;
    border-radius: 50%;
    background: var(--butter);
    top: 12px;
    left: 12px;
    z-index: 0;
  }

  .photo {
    position: relative;
    z-index: 1;
    width: 200px;
    height: 200px;
    border-radius: 50%;
    object-fit: cover;
    border: 3px solid white;
    display: block;
  }

  .photo-label {
    position: absolute;
    z-index: 2;
    bottom: -4px;
    right: -10px;
    background: white;
    border: 1px solid var(--line);
    border-radius: 20px;
    padding: 4px 13px;
    font-size: 10px;
    font-weight: 500;
    color: var(--text-soft);
    letter-spacing: 1.5px;
  }

  /* ── name ── */
  .name-block {
    text-align: center;
    margin-bottom: 44px;
    opacity: 0;
    animation: riseUp 0.8s 0.35s cubic-bezier(0.22,1,0.36,1) forwards;
  }

  .name {
    font-family: 'DM Serif Display', serif;
    font-size: 46px;
    line-height: 1;
    letter-spacing: -1px;
    color: var(--text);
    margin-bottom: 10px;
  }

  .name em {
    font-style: italic;
    color: var(--text-soft);
    font-size: 38px;
  }

  .name-dots {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 10px;
    font-size: 10px;
    letter-spacing: 2.5px;
    color: var(--text-soft);
    text-transform: uppercase;
  }

  .dot-div { width: 3px; height: 3px; border-radius: 50%; background: var(--butter-dark); }

  /* ── divider ── */
  .divider {
    width: 100%;
    height: 1px;
    background: var(--line);
    margin: 0 0 32px;
    opacity: 0;
    animation: fadeIn 0.5s 0.5s forwards;
  }

  /* ── rows ── */
  .rows {
    width: 100%;
    display: flex;
    flex-direction: column;
    gap: 0;
    margin-bottom: 44px;
    opacity: 0;
    animation: riseUp 0.8s 0.5s cubic-bezier(0.22,1,0.36,1) forwards;
  }

  .row {
    display: flex;
    align-items: flex-start;
    padding: 16px 0;
    border-bottom: 1px solid var(--line);
    gap: 20px;
  }

  .row:first-child { border-top: 1px solid var(--line); }

  .row-key {
    font-size: 9px;
    letter-spacing: 2.5px;
    text-transform: uppercase;
    color: var(--text-soft);
    width: 68px;
    flex-shrink: 0;
    padding-top: 2px;
  }

  .row-val {
    flex: 1;
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
    align-items: center;
  }

  /* tags */
  .chip {
    display: inline-block;
    padding: 4px 12px;
    border-radius: 30px;
    font-size: 11px;
    font-weight: 400;
    border: 1px solid transparent;
    line-height: 1.5;
  }

  .ch-y  { background: #FBF0C0; border-color: #E8D060; color: #7A6010; }
  .ch-p  { background: #EDE8F8; border-color: #C8B8F0; color: #6040A0; }
  .ch-pk { background: #FDE8EE; border-color: #F0B8C8; color: #B05070; }
  .ch-m  { background: #E8F5EE; border-color: #A8D8BC; color: #3A7A58; }
  .ch-b  { background: #E8F0F8; border-color: #A8C8E8; color: #305888; }

  .plain-val {
    font-size: 12px;
    color: var(--text);
    font-weight: 400;
  }

  /* bar */
  .bar-group { display: flex; flex-direction: column; gap: 9px; width: 100%; }
  .bar-row { display: flex; align-items: center; gap: 10px; }
  .bar-lbl { font-size: 10px; color: var(--text-soft); width: 60px; flex-shrink: 0; }
  .bar-bg { flex: 1; height: 4px; background: var(--butter); border-radius: 4px; overflow: hidden; }
  .bar-fill { height: 100%; border-radius: 4px; background: var(--butter-dark); animation: grow 1.4s cubic-bezier(0.34,1.1,0.64,1) both; }
  .bar-fill.delay1 { animation-delay: 0.6s; }
  .bar-fill.delay2 { animation-delay: 0.8s; }
  .bar-fill.delay3 { animation-delay: 1.0s; }
  @keyframes grow { from { width: 0 !important; } }
  .bar-num { font-size: 10px; color: var(--text-soft); width: 22px; text-align: right; }

  /* ── links ── */
  .links {
    width: 100%;
    display: flex;
    flex-direction: column;
    gap: 10px;
    margin-bottom: 52px;
    opacity: 0;
    animation: riseUp 0.8s 0.7s cubic-bezier(0.22,1,0.36,1) forwards;
  }

  .links-title {
    font-size: 9px;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: var(--text-soft);
    text-align: center;
    margin-bottom: 6px;
  }

  .lcard {
    display: flex;
    align-items: center;
    gap: 14px;
    background: white;
    border: 1px solid var(--line);
    border-radius: 16px;
    padding: 14px 16px;
    text-decoration: none;
    color: var(--text);
    transition: background 0.2s, transform 0.2s;
  }

  .lcard:hover {
    background: var(--cream);
    transform: translateY(-2px);
  }

  .lcard-icon {
    width: 36px;
    height: 36px;
    background: var(--butter);
    border-radius: 10px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 17px;
    flex-shrink: 0;
  }

  .lcard-label { font-size: 9px; letter-spacing: 2px; text-transform: uppercase; color: var(--text-soft); margin-bottom: 2px; }
  .lcard-name { font-size: 12px; font-weight: 500; }
  .lcard-arrow { margin-left: auto; font-size: 14px; color: var(--text-soft); transition: transform 0.2s; }
  .lcard:hover .lcard-arrow { transform: translateX(3px); }

  /* ── stamp ── */
  .stamp {
    opacity: 0;
    animation: fadeIn 0.6s 0.9s forwards;
    text-align: center;
  }

  .stamp-ring {
    display: inline-block;
    border: 1px dashed var(--butter-dark);
    border-radius: 50px;
    padding: 9px 28px;
    font-size: 10px;
    letter-spacing: 2.5px;
    color: var(--text-soft);
    text-transform: uppercase;
  }

  /* floating click hearts */
  .heart-float {
    position: fixed;
    pointer-events: none;
    z-index: 999;
    font-size: 14px;
    animation: heartUp 1.6s ease forwards;
    opacity: 0;
  }

  @keyframes heartUp {
    0%   { opacity: 1; transform: translateY(0) scale(1); }
    100% { opacity: 0; transform: translateY(-70px) scale(0.4); }
  }

  /* animations */
  @keyframes fadeIn {
    from { opacity: 0; }
    to   { opacity: 1; }
  }

  @keyframes riseUp {
    from { opacity: 0; transform: translateY(18px); }
    to   { opacity: 1; transform: translateY(0); }
  }
</style>
</head>
<body>
<div class="page">

  <!-- ticker -->
  <div class="ticker">
    <div class="ticker-inner">
      <span class="ticker-text">♡ 부쟈의 프로필 &nbsp;·&nbsp; bl gl hl 다먹음 &nbsp;·&nbsp; 마누라 앓이 전문 &nbsp;·&nbsp; 꽃길만 걸어요 &nbsp;·&nbsp; 블언블 &nbsp;·&nbsp; 성인 &nbsp;·&nbsp;</span>
      <span class="ticker-text">♡ 부쟈의 프로필 &nbsp;·&nbsp; bl gl hl 다먹음 &nbsp;·&nbsp; 마누라 앓이 전문 &nbsp;·&nbsp; 꽃길만 걸어요 &nbsp;·&nbsp; 블언블 &nbsp;·&nbsp; 성인 &nbsp;·&nbsp;</span>
    </div>
  </div>

  <!-- photo -->
  <div class="photo-wrap">
    <div class="photo-deco"></div>
    <img
      class="photo"
      src="https://raw.githubusercontent.com/dys1537-netizen/obj/refs/heads/main/from-PixAI-2006824781371567093-1.png"
      alt="부쟈"
    />
    <span class="photo-label">성인 ✦</span>
  </div>

  <!-- name -->
  <div class="name-block">
    <div class="name">부쟈 <em>♡</em></div>
    <div class="name-dots">
      <span>성인</span>
      <span class="dot-div"></span>
      <span>블언블</span>
      <span class="dot-div"></span>
      <span>마누라 앓이 95%</span>
    </div>
  </div>

  <div class="divider"></div>

  <!-- info rows -->
  <div class="rows">

    <div class="row">
      <span class="row-key">Platform</span>
      <div class="row-val">
        <a href="https://tingle.chat/chat/my/profile?tab=characters" target="_blank" class="chip ch-pk">팅글</a>
        <a href="https://www.whif.io/profile/OBJ707" target="_blank" class="chip ch-p">위프</a>
        <span class="chip ch-b">블룸</span>
        <a href="https://rofan.ai/user/240e78f1-b357-40c4-b877-9839418f2208" target="_blank" class="chip ch-y">로판</a>
      </div>
    </div>

    <div class="row">
      <span class="row-key">트윗</span>
      <div class="row-val">
        <span class="chip ch-pk">맘찍</span>
        <span class="chip ch-p">일상</span>
        <span class="chip ch-m">앓이</span>
      </div>
    </div>

    <div class="row">
      <span class="row-key">활동</span>
      <div class="row-val">
        <div class="bar-group">
          <div class="bar-row">
            <span class="bar-lbl">마누라 앓이</span>
            <div class="bar-bg"><div class="bar-fill delay1" style="width:95%;background:var(--pink);"></div></div>
            <span class="bar-num">95%</span>
          </div>
          <div class="bar-row">
            <span class="bar-lbl">소비</span>
            <div class="bar-bg"><div class="bar-fill delay2" style="width:40%"></div></div>
            <span class="bar-num">4%</span>
          </div>
          <div class="bar-row">
            <span class="bar-lbl">제작</span>
            <div class="bar-bg"><div class="bar-fill delay3" style="width:10%"></div></div>
            <span class="bar-num">1%</span>
          </div>
        </div>
      </div>
    </div>

    <div class="row">
      <span class="row-key">장르</span>
      <div class="row-val">
        <span class="plain-val">다 먹음 🍰</span>
      </div>
    </div>

    <div class="row">
      <span class="row-key">커플링</span>
      <div class="row-val">
        <span class="chip ch-p">BL</span>
        <span class="chip ch-pk">GL</span>
        <span class="chip ch-m">HL</span>
        <span class="plain-val" style="font-size:11px;color:var(--text-soft)">· 다 먹음</span>
      </div>
    </div>

    <div class="row">
      <span class="row-key">NG</span>
      <div class="row-val">
        <span class="plain-val">알아서 피함 &nbsp;·&nbsp; 블언블</span>
      </div>
    </div>

  </div>

  <!-- links -->
  <div class="links">
    <div class="links-title">✦ profiles ✦</div>

    <a class="lcard" href="https://tingle.chat/chat/my/profile?tab=characters" target="_blank" rel="noopener">
      <div class="lcard-icon">🌸</div>
      <div>
        <div class="lcard-label">Tingle</div>
        <div class="lcard-name">팅글 프로필</div>
      </div>
      <div class="lcard-arrow">→</div>
    </a>

    <a class="lcard" href="https://www.whif.io/profile/OBJ707" target="_blank" rel="noopener">
      <div class="lcard-icon">💜</div>
      <div>
        <div class="lcard-label">Whif</div>
        <div class="lcard-name">위프 프로필</div>
      </div>
      <div class="lcard-arrow">→</div>
    </a>

    <a class="lcard" href="https://rofan.ai/user/240e78f1-b357-40c4-b877-9839418f2208" target="_blank" rel="noopener">
      <div class="lcard-icon">📖</div>
      <div>
        <div class="lcard-label">Rofan</div>
        <div class="lcard-name">로판 프로필</div>
      </div>
      <div class="lcard-arrow">→</div>
    </a>

  </div>

  <!-- stamp -->
  <div class="stamp">
    <div class="stamp-ring">✦ 부쟈 &nbsp;·&nbsp; since 성인 &nbsp;·&nbsp; 꽃길만 ✦</div>
  </div>

</div>

<script>
  document.body.addEventListener('click', (e) => {
    const marks = ['♡', '✦', '✧', '☆'];
    const colors = ['#F2B8C0', '#E8D060', '#C8B8F0', '#A8D8BC'];
    const h = document.createElement('div');
    h.className = 'heart-float';
    h.textContent = marks[Math.floor(Math.random() * marks.length)];
    h.style.left = e.clientX + 'px';
    h.style.top = e.clientY + 'px';
    h.style.color = colors[Math.floor(Math.random() * colors.length)];
    document.body.appendChild(h);
    setTimeout(() => h.remove(), 1600);
  });
</script>
</body>
</html>
