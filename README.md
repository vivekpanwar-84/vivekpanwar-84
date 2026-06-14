<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Vivek Panwar — GitHub Profile</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&family=Rajdhani:wght@400;600;700&display=swap');
  * { box-sizing: border-box; margin: 0; padding: 0; }
  body { background: #0a0a1a; }
  .profile-root { font-family: 'Rajdhani', sans-serif; background: #0a0a1a; min-height: 100vh; overflow-x: hidden; position: relative; }
  #stars { position: fixed; top: 0; left: 0; width: 100%; height: 100%; pointer-events: none; z-index: 0; }
  .star { position: absolute; background: white; border-radius: 50%; animation: twinkle var(--d) ease-in-out infinite alternate; }
  @keyframes twinkle { from { opacity: 0.1; transform: scale(0.8); } to { opacity: 1; transform: scale(1.3); } }
  .banner { position: relative; z-index: 1; width: 100%; height: 200px; overflow: hidden; }
  .particle { position: absolute; border-radius: 50%; animation: float-up linear infinite; opacity: 0.7; }
  @keyframes float-up { 0% { transform: translateY(200px) rotate(0deg); opacity: 0; } 10% { opacity: 0.7; } 90% { opacity: 0.7; } 100% { transform: translateY(-50px) rotate(360deg); opacity: 0; } }
  .card { position: relative; z-index: 2; margin: -40px 20px 20px; background: rgba(15,15,35,0.97); border: 1px solid rgba(100,80,255,0.3); border-radius: 20px; padding: 24px; box-shadow: 0 0 40px rgba(100,80,255,0.2); }
  .avatar-wrap { display: flex; justify-content: center; margin-top: -70px; margin-bottom: 16px; position: relative; z-index: 3; }
  .avatar-ring { position: relative; width: 100px; height: 100px; }
  .avatar-ring svg { position: absolute; top: 0; left: 0; width: 100%; height: 100%; animation: spin 4s linear infinite; }
  @keyframes spin { to { transform: rotate(360deg); } }
  .avatar-inner { position: absolute; inset: 8px; border-radius: 50%; background: linear-gradient(135deg, #1a1a4e, #2a1a6e); display: flex; align-items: center; justify-content: center; font-family: 'Orbitron', sans-serif; font-size: 28px; font-weight: 900; color: #a78bfa; text-shadow: 0 0 20px #a78bfa; }
  .hero-name { font-family: 'Orbitron', sans-serif; font-size: 26px; font-weight: 900; text-align: center; background: linear-gradient(90deg, #a78bfa, #60a5fa, #34d399, #a78bfa); background-size: 200% 100%; -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text; animation: shimmer 3s linear infinite; margin-bottom: 4px; }
  @keyframes shimmer { from { background-position: 0% } to { background-position: 200% } }
  .hero-sub { text-align: center; color: #94a3b8; font-size: 14px; font-weight: 600; letter-spacing: 2px; text-transform: uppercase; margin-bottom: 6px; }
  .hero-location { text-align: center; font-size: 13px; color: #60a5fa; margin-bottom: 20px; }
  .badges { display: flex; flex-wrap: wrap; gap: 8px; justify-content: center; margin-bottom: 20px; }
  .badge { display: flex; align-items: center; gap: 6px; padding: 6px 14px; border-radius: 20px; font-size: 13px; font-weight: 600; border: 1px solid; position: relative; overflow: hidden; }
  .badge::before { content: ''; position: absolute; inset: 0; background: linear-gradient(90deg, transparent, rgba(255,255,255,0.08), transparent); transform: translateX(-100%); animation: sweep 2.5s ease-in-out infinite; }
  @keyframes sweep { 0% { transform: translateX(-100%); } 60%,100% { transform: translateX(100%); } }
  .badge-green  { color: #34d399; border-color: rgba(52,211,153,0.4); background: rgba(52,211,153,0.08); }
  .badge-blue   { color: #60a5fa; border-color: rgba(96,165,250,0.4); background: rgba(96,165,250,0.08); }
  .badge-purple { color: #a78bfa; border-color: rgba(167,139,250,0.4); background: rgba(167,139,250,0.08); }
  .badge-yellow { color: #fbbf24; border-color: rgba(251,191,36,0.4); background: rgba(251,191,36,0.08); }
  .divider { height: 1px; background: linear-gradient(90deg, transparent, rgba(167,139,250,0.4), transparent); margin: 16px 0; }
  .section-title { font-family: 'Orbitron', sans-serif; font-size: 13px; font-weight: 700; color: #a78bfa; text-transform: uppercase; letter-spacing: 3px; margin-bottom: 14px; display: flex; align-items: center; gap: 8px; }
  .section-title::after { content: ''; flex: 1; height: 1px; background: linear-gradient(90deg, rgba(167,139,250,0.4), transparent); }
  .skill-category-label { font-size: 12px; color: #64748b; font-weight: 600; letter-spacing: 1px; margin-bottom: 8px; margin-top: 4px; text-transform: uppercase; }
  .skills-grid { display: flex; flex-wrap: wrap; gap: 9px; margin-bottom: 12px; }
  .skill-chip { display: flex; align-items: center; gap: 8px; padding: 8px 14px; border-radius: 10px; font-size: 13px; font-weight: 600; border: 1px solid rgba(255,255,255,0.1); background: rgba(255,255,255,0.04); color: #e2e8f0; transition: all 0.3s; cursor: default; }
  .skill-chip:hover { transform: translateY(-3px) scale(1.05); box-shadow: 0 8px 25px rgba(167,139,250,0.3); border-color: rgba(167,139,250,0.5); background: rgba(167,139,250,0.12); }
  .skill-icon { font-size: 18px; }
  .power-bar-wrap { margin-bottom: 8px; }
  .power-label { display: flex; justify-content: space-between; font-size: 12px; color: #94a3b8; margin-bottom: 4px; font-weight: 600; }
  .power-track { height: 6px; background: rgba(255,255,255,0.08); border-radius: 3px; overflow: hidden; }
  .power-fill { height: 100%; border-radius: 3px; animation: fillBar 1.5s cubic-bezier(0.23,1,0.32,1) forwards; }
  @keyframes fillBar { from { width: 0%; } }
  /* STREAK */
  .streak-box { background: rgba(251,191,36,0.06); border: 1px solid rgba(251,191,36,0.25); border-radius: 14px; padding: 16px; text-align: center; margin-bottom: 12px; }
  .streak-num { font-family: 'Orbitron', sans-serif; font-size: 36px; font-weight: 900; color: #fbbf24; text-shadow: 0 0 20px rgba(251,191,36,0.5); animation: pulse-glow 2s ease-in-out infinite; }
  @keyframes pulse-glow { 0%,100% { text-shadow: 0 0 15px rgba(251,191,36,0.4); } 50% { text-shadow: 0 0 30px rgba(251,191,36,0.8), 0 0 60px rgba(251,191,36,0.3); } }
  .streak-row { display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 8px; margin-bottom: 14px; }
  .s-mini { background: rgba(255,255,255,0.04); border: 1px solid rgba(255,255,255,0.08); border-radius: 10px; padding: 12px; text-align: center; }
  .s-mini-num { font-family: 'Orbitron', sans-serif; font-size: 20px; font-weight: 700; }
  .s-mini-lbl { font-size: 11px; color: #94a3b8; margin-top: 3px; }
  /* GitHub stat cards */
  .gh-cards { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; margin-bottom: 14px; }
  .gh-card { background: rgba(167,139,250,0.06); border: 1px solid rgba(167,139,250,0.2); border-radius: 12px; overflow: hidden; }
  .gh-card img { width: 100%; display: block; }
  .gh-card-single { grid-column: 1 / -1; }
  .socials { display: flex; flex-wrap: wrap; gap: 10px; justify-content: center; margin-top: 12px; }
  .social-btn { display: flex; align-items: center; gap: 8px; padding: 10px 20px; border-radius: 12px; font-size: 14px; font-weight: 700; text-decoration: none; border: 1px solid; transition: all 0.3s; font-family: 'Rajdhani', sans-serif; }
  .social-btn:hover { transform: translateY(-3px); box-shadow: 0 10px 30px rgba(0,0,0,0.4); }
  .social-li  { color: #60a5fa; border-color: rgba(96,165,250,0.4); background: rgba(96,165,250,0.08); }
  .social-ig  { color: #f472b6; border-color: rgba(244,114,182,0.4); background: rgba(244,114,182,0.08); }
  .social-gh  { color: #a78bfa; border-color: rgba(167,139,250,0.4); background: rgba(167,139,250,0.08); }
  .fun-fact { text-align: center; font-size: 13px; color: #94a3b8; margin-top: 16px; font-style: italic; padding: 12px; border: 1px dashed rgba(167,139,250,0.25); border-radius: 10px; background: rgba(167,139,250,0.05); }
  .fun-fact span { color: #a78bfa; }
  .anime-char { position: absolute; right: 16px; top: -30px; width: 70px; height: 70px; animation: bob 2.5s ease-in-out infinite; z-index: 10; }
  @keyframes bob { 0%,100% { transform: translateY(0); } 50% { transform: translateY(-8px); } }
  .header-bar { display: flex; justify-content: space-between; align-items: center; padding: 8px 20px 0; position: relative; z-index: 5; }
  .github-chip { display: inline-flex; align-items: center; gap: 5px; font-size: 12px; color: #e2e8f0; background: rgba(255,255,255,0.08); padding: 4px 12px; border-radius: 20px; border: 1px solid rgba(255,255,255,0.12); font-family: 'Orbitron', sans-serif; font-weight: 700; letter-spacing: 1px; }
  .viewer { display: inline-flex; align-items: center; gap: 5px; font-size: 12px; color: #64748b; background: rgba(255,255,255,0.05); padding: 4px 10px; border-radius: 20px; border: 1px solid rgba(255,255,255,0.07); }
  .viewer-dot { width: 6px; height: 6px; background: #34d399; border-radius: 50%; animation: pulse 1.5s ease-in-out infinite; }
  @keyframes pulse { 0%,100% { box-shadow: 0 0 0 0 rgba(52,211,153,0.6); } 50% { box-shadow: 0 0 0 5px rgba(52,211,153,0); } }
  /* SNAKE GAME */
  .snake-section { position: relative; z-index: 2; margin: 0 20px 24px; background: rgba(10,10,30,0.98); border: 1px solid rgba(52,211,153,0.3); border-radius: 18px; padding: 18px; }
  .snake-title-bar { font-family: 'Orbitron', sans-serif; font-size: 13px; font-weight: 700; color: #34d399; letter-spacing: 2px; text-align: center; margin-bottom: 10px; }
  canvas#snakeCanvas { display: block; margin: 0 auto; border: 1px solid rgba(52,211,153,0.2); border-radius: 8px; background: #050510; }
  .snake-controls { display: flex; gap: 8px; justify-content: center; margin-top: 10px; flex-wrap: wrap; align-items: center; }
  .sctl { padding: 7px 16px; border-radius: 8px; font-size: 12px; font-weight: 700; border: 1px solid rgba(52,211,153,0.4); background: rgba(52,211,153,0.08); color: #34d399; cursor: pointer; font-family: 'Rajdhani', sans-serif; transition: all 0.2s; }
  .sctl:hover { background: rgba(52,211,153,0.2); }
  .arrow-pad { display: grid; grid-template-columns: repeat(3, 42px); grid-template-rows: repeat(2, 42px); gap: 5px; justify-content: center; margin-top: 10px; }
  .abtn { width: 42px; height: 42px; border-radius: 8px; font-size: 16px; border: 1px solid rgba(52,211,153,0.3); background: rgba(52,211,153,0.07); color: #34d399; cursor: pointer; display: flex; align-items: center; justify-content: center; transition: all 0.15s; }
  .abtn:active { background: rgba(52,211,153,0.3); transform: scale(0.9); }
</style>
</head>
<body>
<div class="profile-root">
<div id="stars"></div>

<!-- BANNER -->
<div class="banner">
  <svg width="100%" viewBox="0 0 680 200" xmlns="http://www.w3.org/2000/svg">
    <defs>
      <linearGradient id="bg" x1="0%" y1="0%" x2="100%" y2="100%"><stop offset="0%" stop-color="#0d0d2b"/><stop offset="50%" stop-color="#1a0a3d"/><stop offset="100%" stop-color="#0a1a4d"/></linearGradient>
      <linearGradient id="wave1" x1="0%" y1="0%" x2="100%" y2="0%"><stop offset="0%" stop-color="#6d28d9" stop-opacity="0.6"/><stop offset="100%" stop-color="#2563eb" stop-opacity="0.3"/></linearGradient>
      <linearGradient id="wave2" x1="0%" y1="0%" x2="100%" y2="0%"><stop offset="0%" stop-color="#2563eb" stop-opacity="0.3"/><stop offset="100%" stop-color="#059669" stop-opacity="0.4"/></linearGradient>
    </defs>
    <rect width="680" height="200" fill="url(#bg)"/>
    <g stroke="rgba(100,80,255,0.12)" stroke-width="0.5">
      <line x1="0" y1="40"  x2="680" y2="40"/><line x1="0" y1="80"  x2="680" y2="80"/>
      <line x1="0" y1="120" x2="680" y2="120"/><line x1="0" y1="160" x2="680" y2="160"/>
      <line x1="136" y1="0" x2="136" y2="200"/><line x1="272" y1="0" x2="272" y2="200"/>
      <line x1="408" y1="0" x2="408" y2="200"/><line x1="544" y1="0" x2="544" y2="200"/>
    </g>
    <path d="M0 120 Q170 80 340 130 Q510 180 680 110 L680 200 L0 200Z" fill="url(#wave1)"/>
    <path d="M0 150 Q170 110 340 160 Q510 200 680 140 L680 200 L0 200Z" fill="url(#wave2)"/>
    <circle cx="60"  cy="50" r="30" fill="#6d28d9" opacity="0.15"/><circle cx="60"  cy="50" r="15" fill="#a78bfa" opacity="0.25"/>
    <circle cx="620" cy="40" r="40" fill="#2563eb" opacity="0.12"/><circle cx="620" cy="40" r="20" fill="#60a5fa" opacity="0.2"/>
    <circle cx="340" cy="90" r="50" fill="#059669" opacity="0.08"/>
    <g fill="rgba(167,139,250,0.5)">
      <polygon points="100,30 108,38 100,46 92,38"/><polygon points="550,60 558,68 550,76 542,68" transform="rotate(15 550 68)"/>
      <polygon points="200,160 207,167 200,174 193,167" transform="rotate(-10 200 167)"/><polygon points="480,130 487,137 480,144 473,137" transform="rotate(5 480 137)"/>
    </g>
    <text x="340" y="75"  text-anchor="middle" font-family="Orbitron,monospace" font-size="11" font-weight="700" fill="#a78bfa" letter-spacing="6" opacity="0.8">DEVELOPER PROFILE</text>
    <text x="340" y="108" text-anchor="middle" font-family="Orbitron,monospace" font-size="28" font-weight="900" fill="white" letter-spacing="2">VIVEK PANWAR</text>
    <text x="340" y="135" text-anchor="middle" font-family="Rajdhani,sans-serif" font-size="13" font-weight="600" fill="#60a5fa" letter-spacing="4">✦ FULL STACK DEVELOPER · INDIA ✦</text>
    <text x="340" y="158" text-anchor="middle" font-family="Rajdhani,sans-serif" font-size="11" fill="#94a3b8" letter-spacing="1">MERN Stack · React · Node.js · MongoDB · Express</text>
  </svg>
  <div id="particles"></div>
</div>

<div class="header-bar">
  <div class="github-chip">⚡ vivekpanwar-84</div>
  <div class="viewer"><span class="viewer-dot"></span> Profile active</div>
</div>

<!-- MAIN CARD -->
<div class="card" style="position:relative;">
  <!-- Anime character -->
  <div class="anime-char">
    <svg viewBox="0 0 70 70" xmlns="http://www.w3.org/2000/svg">
      <circle cx="35" cy="35" r="32" fill="rgba(167,139,250,0.12)"/>
      <ellipse cx="35" cy="52" rx="22" ry="14" fill="#4c1d95"/>
      <rect x="24" y="38" width="22" height="18" rx="4" fill="#6d28d9"/>
      <circle cx="35" cy="28" r="14" fill="#fde68a"/>
      <path d="M21 22 Q25 10 35 12 Q45 10 49 22 Q47 15 35 14 Q23 15 21 22Z" fill="#1e1b4b"/>
      <path d="M22 20 Q18 10 22 8 Q24 16 24 20Z" fill="#1e1b4b"/>
      <path d="M48 20 Q52 10 48 8 Q46 16 46 20Z" fill="#1e1b4b"/>
      <path d="M35 12 Q33 4 36 2 Q38 8 36 12Z" fill="#1e1b4b"/>
      <ellipse cx="29" cy="28" rx="4" ry="5" fill="white"/><ellipse cx="41" cy="28" rx="4" ry="5" fill="white"/>
      <circle cx="30" cy="29" r="2.5" fill="#6d28d9"/><circle cx="42" cy="29" r="2.5" fill="#6d28d9"/>
      <circle cx="31" cy="28" r="1" fill="white"/><circle cx="43" cy="28" r="1" fill="white"/>
      <path d="M29 35 Q35 40 41 35" stroke="#e11d48" stroke-width="1.5" fill="none" stroke-linecap="round"/>
      <ellipse cx="25" cy="34" rx="4" ry="2" fill="rgba(244,114,182,0.4)"/><ellipse cx="45" cy="34" rx="4" ry="2" fill="rgba(244,114,182,0.4)"/>
      <text x="35" y="52" text-anchor="middle" font-size="10" fill="#fbbf24">★</text>
    </svg>
  </div>

  <!-- Avatar -->
  <div class="avatar-wrap">
    <div class="avatar-ring">
      <svg viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg">
        <defs><linearGradient id="ringGrad" x1="0%" y1="0%" x2="100%" y2="100%"><stop offset="0%" stop-color="#a78bfa"/><stop offset="50%" stop-color="#60a5fa"/><stop offset="100%" stop-color="#34d399"/></linearGradient></defs>
        <circle cx="50" cy="50" r="46" fill="none" stroke="#1e1b4b" stroke-width="4"/>
        <circle cx="50" cy="50" r="46" fill="none" stroke="url(#ringGrad)" stroke-width="3" stroke-dasharray="8 4" stroke-linecap="round"/>
      </svg>
      <div class="avatar-inner">VP</div>
    </div>
  </div>

  <div class="hero-name">Vivek Panwar</div>
  <div class="hero-sub">Full Stack Developer</div>
  <div class="hero-location">📍 Indore, India &nbsp;·&nbsp; 🎓 CSE 2026 &nbsp;·&nbsp; 🌱 Learning & Building</div>

  <div class="badges">
    <div class="badge badge-green">🟢 Open to work</div>
    <div class="badge badge-blue">💻 MERN Stack Dev</div>
    <div class="badge badge-purple">⚡ Full Stack</div>
    <div class="badge badge-yellow">🏆 2 Internships</div>
  </div>

  <div class="divider"></div>

  <!-- ===== SKILLS ===== -->
  <div class="section-title">⚔ Arsenal / Skills</div>

  <div class="skill-category-label">— Languages —</div>
  <div class="skills-grid">
    <div class="skill-chip"><span class="skill-icon">⚙</span> C / C++</div>
    <div class="skill-chip"><span class="skill-icon">⚡</span> JavaScript</div>
    <div class="skill-chip"><span class="skill-icon">🌐</span> HTML5</div>
    <div class="skill-chip"><span class="skill-icon">🎨</span> CSS3</div>
    <div class="skill-chip"><span class="skill-icon">🌊</span> Tailwind CSS</div>
  </div>

  <div class="skill-category-label">— Frontend —</div>
  <div class="skills-grid">
    <div class="skill-chip"><span class="skill-icon">⚛</span> React.js</div>
    <div class="skill-chip"><span class="skill-icon">📱</span> Responsive UI/UX</div>
  </div>

  <div class="skill-category-label">— Backend &amp; Tools —</div>
  <div class="skills-grid">
    <div class="skill-chip"><span class="skill-icon">🟢</span> Node.js</div>
    <div class="skill-chip"><span class="skill-icon">🚀</span> Express.js</div>
    <div class="skill-chip"><span class="skill-icon">🔗</span> REST APIs</div>
    <div class="skill-chip"><span class="skill-icon">🔐</span> JWT Auth</div>
    <div class="skill-chip"><span class="skill-icon">🐙</span> Git / GitHub</div>
    <div class="skill-chip"><span class="skill-icon">📮</span> Postman</div>
  </div>

  <div class="skill-category-label">— Database —</div>
  <div class="skills-grid" style="margin-bottom:0">
    <div class="skill-chip"><span class="skill-icon">🍃</span> MongoDB</div>
    <div class="skill-chip"><span class="skill-icon">🗄</span> MySQL</div>
  </div>

  <div class="divider"></div>

  <!-- POWER LEVELS -->
  <div class="section-title">🔥 Power Level</div>
  <div class="power-bar-wrap"><div class="power-label"><span>React.js / Frontend</span><span style="color:#34d399">★★★★★ 90%</span></div><div class="power-track"><div class="power-fill" style="width:90%;background:linear-gradient(90deg,#059669,#34d399)"></div></div></div>
  <div class="power-bar-wrap" style="margin-top:8px"><div class="power-label"><span>Node.js / Express</span><span style="color:#60a5fa">★★★★★ 85%</span></div><div class="power-track"><div class="power-fill" style="width:85%;background:linear-gradient(90deg,#1d4ed8,#60a5fa);animation-delay:.15s"></div></div></div>
  <div class="power-bar-wrap" style="margin-top:8px"><div class="power-label"><span>MongoDB</span><span style="color:#34d399">★★★★☆ 80%</span></div><div class="power-track"><div class="power-fill" style="width:80%;background:linear-gradient(90deg,#059669,#34d399);animation-delay:.3s"></div></div></div>
  <div class="power-bar-wrap" style="margin-top:8px"><div class="power-label"><span>JavaScript</span><span style="color:#fbbf24">★★★★☆ 78%</span></div><div class="power-track"><div class="power-fill" style="width:78%;background:linear-gradient(90deg,#b45309,#fbbf24);animation-delay:.45s"></div></div></div>
  <div class="power-bar-wrap" style="margin-top:8px"><div class="power-label"><span>HTML / CSS / Tailwind</span><span style="color:#a78bfa">★★★★☆ 82%</span></div><div class="power-track"><div class="power-fill" style="width:82%;background:linear-gradient(90deg,#5b21b6,#a78bfa);animation-delay:.6s"></div></div></div>
  <div class="power-bar-wrap" style="margin-top:8px"><div class="power-label"><span>C / C++</span><span style="color:#f472b6">★★★☆☆ 65%</span></div><div class="power-track"><div class="power-fill" style="width:65%;background:linear-gradient(90deg,#9d174d,#f472b6);animation-delay:.75s"></div></div></div>
  <div class="power-bar-wrap" style="margin-top:8px"><div class="power-label"><span>MySQL</span><span style="color:#f59e0b">★★★☆☆ 60%</span></div><div class="power-track"><div class="power-fill" style="width:60%;background:linear-gradient(90deg,#92400e,#f59e0b);animation-delay:.9s"></div></div></div>

  <div class="divider"></div>

  <!-- STREAK & STATS -->
  <div class="section-title">🔥 GitHub Streak</div>
  <div class="streak-box">
    <div style="font-size:11px;color:#94a3b8;letter-spacing:2px;text-transform:uppercase;margin-bottom:6px">Current Streak 🔥</div>
    <div class="streak-num" id="streakNum">0</div>
    <div style="font-size:12px;color:#94a3b8;margin-top:4px">days coding on GitHub</div>
  </div>
  <div class="streak-row">
    <div class="s-mini"><div class="s-mini-num" style="color:#a78bfa">2</div><div class="s-mini-lbl">Projects</div></div>
    <div class="s-mini"><div class="s-mini-num" style="color:#34d399">2</div><div class="s-mini-lbl">Internships</div></div>
    <div class="s-mini"><div class="s-mini-num" style="color:#60a5fa">15+</div><div class="s-mini-lbl">Skills</div></div>
  </div>

  <div class="divider"></div>

  <!-- GITHUB STAT CARDS -->
  <div class="section-title">📊 Mission Stats</div>
  <div class="gh-cards">
    <div class="gh-card">
      <img src="https://github-readme-stats.vercel.app/api?username=vivekpanwar-84&show_icons=true&theme=tokyonight&hide_border=true&bg_color=0d0d2b&title_color=a78bfa&icon_color=60a5fa&text_color=e2e8f0" alt="Vivek's GitHub Stats" loading="lazy"/>
    </div>
    <div class="gh-card">
      <img src="https://github-readme-stats.vercel.app/api/top-langs?username=vivekpanwar-84&layout=compact&theme=tokyonight&hide_border=true&bg_color=0d0d2b&title_color=a78bfa&text_color=e2e8f0" alt="Top Languages" loading="lazy"/>
    </div>
    <div class="gh-card gh-card-single">
      <img src="https://github-readme-streak-stats.herokuapp.com/?user=vivekpanwar-84&theme=tokyonight&hide_border=true&background=0d0d2b&stroke=a78bfa&ring=60a5fa&fire=fbbf24&currStreakLabel=a78bfa" alt="GitHub Streak" loading="lazy"/>
    </div>
  </div>

  <!-- CONNECT -->
  <div class="section-title">🌐 Connect</div>
  <div class="socials">
    <a class="social-btn social-li" href="https://www.linkedin.com/in/vivek-panwar-484b9425b" target="_blank">
      <svg width="18" height="18" viewBox="0 0 24 24" fill="currentColor"><path d="M16 8a6 6 0 016 6v7h-4v-7a2 2 0 00-2-2 2 2 0 00-2 2v7h-4v-7a6 6 0 016-6zM2 9h4v12H2z"/><circle cx="4" cy="4" r="2"/></svg>
      LinkedIn
    </a>
    <a class="social-btn social-ig" href="https://instagram.com/_v_alentino_" target="_blank">
      <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="2" y="2" width="20" height="20" rx="5" ry="5"/><circle cx="12" cy="12" r="4"/><circle cx="17.5" cy="6.5" r="0.5" fill="currentColor"/></svg>
      Instagram
    </a>
    <a class="social-btn social-gh" href="https://github.com/vivekpanwar-84" target="_blank">
      <svg width="18" height="18" viewBox="0 0 24 24" fill="currentColor"><path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 00-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0020 4.77 5.07 5.07 0 0019.91 1S18.73.65 16 2.48a13.38 13.38 0 00-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 005 4.77a5.44 5.44 0 00-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 009 18.13V22"/></svg>
      GitHub
    </a>
  </div>

  <div class="fun-fact">⚡ Fun fact — <span>I think I am funny 😁</span> &nbsp;·&nbsp; Let's code something amazing together!</div>
</div>

<!-- SNAKE GAME -->
<div class="snake-section">
  <div class="snake-title-bar">🐍 SNAKE GAME &nbsp;|&nbsp; Score: <span id="scoreDisp">0</span> &nbsp;|&nbsp; Best: <span id="bestDisp">0</span></div>
  <canvas id="snakeCanvas" width="320" height="240"></canvas>
  <div class="snake-controls">
    <button class="sctl" id="startBtn" onclick="startGame()">▶ Start</button>
    <button class="sctl" onclick="resetGame()">↺ Reset</button>
    <span style="font-size:11px;color:#64748b">WASD / Arrows / Touch</span>
  </div>
  <div class="arrow-pad">
    <div></div>
    <button class="abtn" onclick="changeDir(0,-1)">▲</button>
    <div></div>
    <button class="abtn" onclick="changeDir(-1,0)">◀</button>
    <button class="abtn" onclick="changeDir(0,1)">▼</button>
    <button class="abtn" onclick="changeDir(1,0)">▶</button>
  </div>
</div>

</div><!-- end profile-root -->

<script>
// Stars
const starsEl=document.getElementById('stars');
for(let i=0;i<80;i++){const s=document.createElement('div');s.className='star';const sz=Math.random()*2.5+.5;s.style.cssText=`width:${sz}px;height:${sz}px;top:${Math.random()*100}%;left:${Math.random()*100}%;--d:${(Math.random()*3+1).toFixed(1)}s;animation-delay:${(Math.random()*3).toFixed(1)}s`;starsEl.appendChild(s)}

// Particles
const pe=document.getElementById('particles');
const pc=['#a78bfa','#60a5fa','#34d399','#f472b6','#fbbf24'];
for(let i=0;i<12;i++){const p=document.createElement('div');p.className='particle';const sz=Math.random()*6+3;const c=pc[Math.floor(Math.random()*pc.length)];const dur=Math.random()*4+3;const dl=Math.random()*4;p.style.cssText=`width:${sz}px;height:${sz}px;left:${Math.random()*100}%;background:${c};animation-duration:${dur}s;animation-delay:${dl}s`;pe.appendChild(p)}

// Streak counter
let sc=0;const si=setInterval(()=>{sc+=2;if(sc>=47){sc=47;clearInterval(si)}document.getElementById('streakNum').textContent=sc},40);

// SNAKE
const canvas=document.getElementById('snakeCanvas');
const ctx=canvas.getContext('2d');
const COLS=16,ROWS=12,SZ=20;
let snake,dir,nextDir,food,score,best=0,loop,running=false,over=false;
function init(){snake=[{x:8,y:6},{x:7,y:6},{x:6,y:6}];dir={x:1,y:0};nextDir={x:1,y:0};score=0;over=false;running=false;placeFood();draw();document.getElementById('scoreDisp').textContent=0}
function placeFood(){let p;do{p={x:Math.floor(Math.random()*COLS),y:Math.floor(Math.random()*ROWS)}}while(snake.some(s=>s.x===p.x&&s.y===p.y));food=p}
function draw(){
  ctx.fillStyle='#050510';ctx.fillRect(0,0,320,240);
  ctx.strokeStyle='rgba(52,211,153,0.06)';ctx.lineWidth=.5;
  for(let x=0;x<=COLS;x++){ctx.beginPath();ctx.moveTo(x*SZ,0);ctx.lineTo(x*SZ,240);ctx.stroke()}
  for(let y=0;y<=ROWS;y++){ctx.beginPath();ctx.moveTo(0,y*SZ);ctx.lineTo(320,y*SZ);ctx.stroke()}
  ctx.shadowBlur=12;ctx.shadowColor='#f472b6';ctx.fillStyle='#f472b6';ctx.beginPath();ctx.arc(food.x*SZ+10,food.y*SZ+10,7,0,Math.PI*2);ctx.fill();ctx.shadowBlur=0;
  snake.forEach((seg,i)=>{const r=i/snake.length;ctx.shadowBlur=i===0?14:0;ctx.shadowColor='#34d399';ctx.fillStyle=i===0?'#34d399':`hsl(${160-r*40},80%,${55-r*15}%)`;ctx.beginPath();ctx.roundRect(seg.x*SZ+1,seg.y*SZ+1,SZ-2,SZ-2,4);ctx.fill();ctx.shadowBlur=0;if(i===0){ctx.fillStyle='#050510';ctx.fillRect(seg.x*SZ+5,seg.y*SZ+5,3,3);ctx.fillRect(seg.x*SZ+12,seg.y*SZ+5,3,3)}});
  if(over){ctx.fillStyle='rgba(5,5,16,.82)';ctx.fillRect(0,80,320,80);ctx.fillStyle='#f472b6';ctx.font='bold 18px Orbitron,monospace';ctx.textAlign='center';ctx.fillText('GAME OVER',160,112);ctx.fillStyle='#94a3b8';ctx.font='13px Rajdhani,sans-serif';ctx.fillText(`Score: ${score}  Best: ${best}`,160,134);ctx.textAlign='left'}
  else if(!running){ctx.fillStyle='rgba(5,5,16,.7)';ctx.fillRect(0,90,320,60);ctx.fillStyle='#34d399';ctx.font='bold 15px Orbitron,monospace';ctx.textAlign='center';ctx.fillText('PRESS START',160,118);ctx.fillStyle='#64748b';ctx.font='11px Rajdhani,sans-serif';ctx.fillText('WASD / Arrow keys / Buttons',160,136);ctx.textAlign='left'}
}
function step(){if(!running||over)return;dir={x:nextDir.x,y:nextDir.y};const h={x:snake[0].x+dir.x,y:snake[0].y+dir.y};if(h.x<0||h.x>=COLS||h.y<0||h.y>=ROWS||snake.some(s=>s.x===h.x&&s.y===h.y)){over=true;running=false;clearInterval(loop);if(score>best){best=score;document.getElementById('bestDisp').textContent=best}draw();return}snake.unshift(h);if(h.x===food.x&&h.y===food.y){score++;document.getElementById('scoreDisp').textContent=score;placeFood()}else snake.pop();draw()}
function changeDir(x,y){if(x!==0&&dir.x!==0)return;if(y!==0&&dir.y!==0)return;nextDir={x,y}}
function startGame(){if(over)init();if(!running){running=true;loop=setInterval(step,130);document.getElementById('startBtn').textContent='⏸ Pause'}else{running=false;clearInterval(loop);document.getElementById('startBtn').textContent='▶ Resume'}}
function resetGame(){clearInterval(loop);document.getElementById('startBtn').textContent='▶ Start';init()}
document.addEventListener('keydown',e=>{const m={'ArrowUp':[0,-1],'ArrowDown':[0,1],'ArrowLeft':[-1,0],'ArrowRight':[1,0],'w':[0,-1],'s':[0,1],'a':[-1,0],'d':[1,0]};if(m[e.key]){e.preventDefault();changeDir(...m[e.key])}if(e.key===' '){e.preventDefault();startGame()}});
init();
</script>
</body>
</html>
