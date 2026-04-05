<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Deneshkar Punyamoorthy — Portfolio</title>
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500;700&family=Syne:wght@400;600;800&display=swap" rel="stylesheet"/>
<style>
  *{margin:0;padding:0;box-sizing:border-box}
  :root{
    --bg:#0a0c10;
    --bg2:#0f1117;
    --bg3:#161b22;
    --border:#21262d;
    --text:#e6edf3;
    --muted:#8b949e;
    --blue:#58a6ff;
    --green:#3fb950;
    --orange:#ff7b72;
    --yellow:#e3b341;
    --purple:#bc8cff;
    --mono:'JetBrains Mono',monospace;
    --sans:'Syne',sans-serif;
  }
  body{background:var(--bg);color:var(--text);font-family:var(--mono);line-height:1.6;min-height:100vh;overflow-x:hidden}

  /* scanline overlay */
  body::before{content:'';position:fixed;inset:0;background:repeating-linear-gradient(0deg,transparent,transparent 2px,rgba(0,0,0,0.03) 2px,rgba(0,0,0,0.03) 4px);pointer-events:none;z-index:9999}

  .container{max-width:860px;margin:0 auto;padding:40px 24px 80px}

  /* HEADER */
  .header{text-align:center;padding:60px 0 40px;position:relative}
  .header::before{content:'';position:absolute;inset:0;background:radial-gradient(ellipse 600px 300px at 50% 0%,rgba(88,166,255,0.07),transparent);pointer-events:none}
  .status-badge{display:inline-flex;align-items:center;gap:8px;background:rgba(63,185,80,0.1);border:1px solid rgba(63,185,80,0.3);color:var(--green);font-size:11px;padding:5px 14px;border-radius:20px;margin-bottom:28px;letter-spacing:0.08em;text-transform:uppercase}
  .dot{width:7px;height:7px;border-radius:50%;background:var(--green);animation:pulse 2s infinite}
  @keyframes pulse{0%,100%{opacity:1;box-shadow:0 0 0 0 rgba(63,185,80,0.4)}50%{opacity:0.8;box-shadow:0 0 0 6px rgba(63,185,80,0)}}
  .name{font-family:var(--sans);font-size:clamp(2rem,6vw,3.2rem);font-weight:800;color:var(--text);letter-spacing:-0.02em;margin-bottom:8px}
  .name span{color:var(--blue)}
  .role{font-size:13px;color:var(--muted);margin-bottom:28px;letter-spacing:0.05em}
  .role .highlight{color:var(--blue)}
  .social-links{display:flex;justify-content:center;gap:10px;flex-wrap:wrap}
  .social-links a{display:inline-flex;align-items:center;gap:7px;background:var(--bg3);border:1px solid var(--border);color:var(--muted);font-size:11px;padding:7px 14px;border-radius:8px;text-decoration:none;transition:all 0.2s;letter-spacing:0.04em}
  .social-links a:hover{border-color:var(--blue);color:var(--blue);background:rgba(88,166,255,0.05)}

  /* SECTION */
  .section{margin-top:44px}
  .section-header{display:flex;align-items:center;gap:10px;margin-bottom:18px;font-size:13px;color:var(--green)}
  .section-header::before{content:'$';color:var(--orange)}
  .section-header span{color:var(--blue)}

  /* WHOAMI BLOCK */
  .terminal-box{background:var(--bg2);border:1px solid var(--border);border-radius:10px;overflow:hidden}
  .terminal-bar{display:flex;align-items:center;gap:7px;padding:10px 16px;background:var(--bg3);border-bottom:1px solid var(--border)}
  .tb{width:11px;height:11px;border-radius:50%}
  .tb-r{background:#ff5f57}.tb-y{background:#febc2e}.tb-g{background:#28c840}
  .terminal-content{padding:18px 20px;font-size:13px;line-height:2}
  .kv{display:grid;grid-template-columns:100px 1fr;gap:0 12px}
  .k{color:var(--blue)}.v{color:var(--text)}
  .v-green{color:var(--green)}.v-yellow{color:var(--yellow)}.v-purple{color:var(--purple)}
  .comment{color:var(--muted)}

  /* STATS GRID */
  .stats-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:12px}
  .stat-card{background:var(--bg2);border:1px solid var(--border);border-radius:10px;padding:20px;text-align:center;transition:border-color 0.2s}
  .stat-card:hover{border-color:var(--blue)}
  .stat-num{font-family:var(--sans);font-size:2rem;font-weight:800;line-height:1}
  .stat-label{font-size:11px;color:var(--muted);margin-top:6px;letter-spacing:0.05em;text-transform:uppercase}
  .stat-sub{font-size:10px;color:var(--muted);margin-top:4px}
  .blue{color:var(--blue)}.green{color:var(--green)}.orange{color:var(--orange)}

  /* STREAK VISUAL */
  .streak-wrap{background:var(--bg2);border:1px solid var(--border);border-radius:10px;padding:22px;text-align:center}
  .streak-ring{width:90px;height:90px;margin:0 auto 12px;position:relative}
  .streak-ring svg{width:100%;height:100%}
  .streak-num{position:absolute;inset:0;display:flex;align-items:center;justify-content:center;font-family:var(--sans);font-size:1.8rem;font-weight:800;color:var(--blue)}
  .streak-title{font-size:12px;color:var(--blue);letter-spacing:0.08em;text-transform:uppercase;margin-bottom:4px}
  .streak-date{font-size:11px;color:var(--muted)}

  /* LANGS BAR */
  .langs-card{background:var(--bg2);border:1px solid var(--border);border-radius:10px;padding:20px}
  .langs-title{font-size:12px;color:var(--muted);letter-spacing:0.06em;text-transform:uppercase;margin-bottom:14px}
  .lang-bar-wrap{display:flex;height:8px;border-radius:6px;overflow:hidden;margin-bottom:14px;gap:2px}
  .lang-bar-wrap div{height:100%;border-radius:3px;transition:flex 0.3s}
  .lang-row{display:flex;flex-wrap:wrap;gap:8px}
  .lang-dot{display:flex;align-items:center;gap:5px;font-size:11px;color:var(--muted)}
  .lang-dot span{width:8px;height:8px;border-radius:50%;display:inline-block}

  /* TECH STACK */
  .stack-section .sub-title{font-size:11px;color:var(--muted);margin:14px 0 8px;letter-spacing:0.06em;text-transform:uppercase;display:flex;align-items:center;gap:8px}
  .stack-section .sub-title::after{content:'';flex:1;height:1px;background:var(--border)}
  .badges{display:flex;flex-wrap:wrap;gap:8px}
  .badge{display:inline-flex;align-items:center;gap:6px;background:var(--bg3);border:1px solid var(--border);color:var(--muted);font-size:11px;padding:5px 11px;border-radius:6px;letter-spacing:0.03em;transition:all 0.2s;cursor:default}
  .badge:hover{transform:translateY(-2px);border-color:var(--blue);color:var(--text)}
  .badge-dot{width:7px;height:7px;border-radius:50%}

  /* PROJECTS */
  .projects-grid{display:grid;grid-template-columns:1fr 1fr;gap:14px}
  .project-card{background:var(--bg2);border:1px solid var(--border);border-radius:10px;padding:20px;transition:border-color 0.2s;position:relative;overflow:hidden}
  .project-card::before{content:'';position:absolute;top:0;left:0;right:0;height:2px;background:linear-gradient(90deg,var(--blue),var(--purple));opacity:0;transition:opacity 0.2s}
  .project-card:hover{border-color:rgba(88,166,255,0.4)}
  .project-card:hover::before{opacity:1}
  .proj-title{font-family:var(--sans);font-size:14px;font-weight:600;color:var(--text);margin-bottom:8px}
  .proj-desc{font-size:12px;color:var(--muted);margin-bottom:14px;line-height:1.7}
  .proj-features{margin-bottom:14px}
  .proj-feat{font-size:11px;color:var(--muted);padding:2px 0;display:flex;align-items:center;gap:6px}
  .proj-feat::before{content:'✦';color:var(--blue);font-size:9px}
  .proj-badges{display:flex;flex-wrap:wrap;gap:5px}
  .proj-badge{font-size:10px;background:var(--bg3);border:1px solid var(--border);color:var(--muted);padding:3px 8px;border-radius:5px}

  /* GOALS */
  .goals-list{display:grid;gap:8px}
  .goal-row{display:flex;align-items:center;gap:12px;background:var(--bg2);border:1px solid var(--border);border-radius:8px;padding:12px 16px;font-size:12px;color:var(--muted);transition:all 0.2s}
  .goal-row:hover{border-color:var(--green);color:var(--text)}
  .goal-icon{color:var(--green);font-size:14px;min-width:20px}

  /* ACTIVITY GRAPH (pure CSS) */
  .activity-wrap{background:var(--bg2);border:1px solid var(--border);border-radius:10px;padding:20px}
  .activity-grid{display:flex;gap:3px;overflow:hidden}
  .activity-col{display:flex;flex-direction:column;gap:3px}
  .activity-cell{width:11px;height:11px;border-radius:2px;background:var(--bg3)}
  .act-0{background:#161b22}.act-1{background:#0e4429}.act-2{background:#006d32}.act-3{background:#26a641}.act-4{background:#39d353}
  .activity-labels{display:flex;justify-content:space-between;font-size:10px;color:var(--muted);margin-top:8px}

  /* FOOTER */
  .footer{text-align:center;margin-top:60px;padding-top:30px;border-top:1px solid var(--border);font-size:11px;color:var(--muted);line-height:2}
  .footer a{color:var(--blue);text-decoration:none}

  /* CONTACT */
  .contact-bar{display:flex;align-items:center;justify-content:center;gap:8px;background:rgba(88,166,255,0.05);border:1px solid rgba(88,166,255,0.2);border-radius:10px;padding:14px 20px;font-size:12px;color:var(--muted);flex-wrap:wrap}
  .contact-bar span{color:var(--blue)}
  .contact-bar .sep{color:var(--border)}

  @media(max-width:620px){
    .stats-grid{grid-template-columns:1fr 1fr}
    .projects-grid{grid-template-columns:1fr}
    .kv{grid-template-columns:90px 1fr}
  }
  @media(max-width:420px){.stats-grid{grid-template-columns:1fr}}
</style>
</head>
<body>
<div class="container">

  <!-- HEADER -->
  <div class="header">
    <div class="status-badge"><span class="dot"></span> Open to Internships 2026</div>
    <div class="name">Deneshkar <span>Punyamoorthy</span></div>
    <div class="role">Full Stack Developer · <span class="highlight">MERN Stack</span> · Sri Lanka 🇱🇰</div>
    <div class="social-links">
      <a href="https://www.linkedin.com/in/deneshkar-punyamoorthy-450931350" target="_blank">⬡ LinkedIn</a>
      <a href="https://github.com/Deneshkar" target="_blank">⬡ GitHub</a>
      <a href="https://instagram.com/_ajith.dk_" target="_blank">⬡ Instagram</a>
      <a href="mailto:deneshkar015@gmail.com">⬡ Email</a>
    </div>
  </div>

  <!-- WHOAMI -->
  <div class="section">
    <div class="section-header"><span>whoami</span></div>
    <div class="terminal-box">
      <div class="terminal-bar"><div class="tb tb-r"></div><div class="tb tb-y"></div><div class="tb tb-g"></div></div>
      <div class="terminal-content">
        <div class="kv">
          <span class="k">Name</span><span class="v">Deneshkar Punyamoorthy</span>
          <span class="k">Role</span><span class="v-purple">Aspiring Software Engineer · Full Stack Developer</span>
          <span class="k">Stack</span><span class="v-blue">MERN (MongoDB · Express · React · Node.js)</span>
          <span class="k">Degree</span><span class="v">B.Sc. (Hons) Information Technology</span>
          <span class="k">Location</span><span class="v">Sri Lanka 🇱🇰</span>
          <span class="k">Status</span><span class="v-green">🟢 Actively seeking Software Engineer Internship</span>
          <span class="k">Goal</span><span class="comment">Building ideas into useful products, one commit at a time</span>
        </div>
      </div>
    </div>
  </div>

  <!-- STATS -->
  <div class="section">
    <div class="section-header"><span>cat github_stats.json</span></div>
    <div class="stats-grid">
      <div class="stat-card">
        <div class="stat-num blue">57</div>
        <div class="stat-label">Total Contributions</div>
        <div class="stat-sub">Mar 2025 – Present</div>
      </div>
      <div class="stat-card" style="border-color:rgba(88,166,255,0.35)">
        <div class="streak-ring">
          <svg viewBox="0 0 90 90">
            <circle cx="45" cy="45" r="36" fill="none" stroke="#21262d" stroke-width="6"/>
            <circle cx="45" cy="45" r="36" fill="none" stroke="#58a6ff" stroke-width="6"
              stroke-dasharray="226" stroke-dashoffset="215" stroke-linecap="round"
              transform="rotate(-90 45 45)"/>
          </svg>
          <div class="streak-num">1</div>
        </div>
        <div class="streak-title">🔥 Current Streak</div>
        <div class="streak-date">Apr 5, 2025</div>
      </div>
      <div class="stat-card">
        <div class="stat-num orange">3</div>
        <div class="stat-label">Longest Streak</div>
        <div class="stat-sub">May 14–16, 2025</div>
      </div>
    </div>

    <!-- LANGUAGES BAR -->
    <div style="margin-top:12px">
      <div class="langs-card">
        <div class="langs-title">Top Languages</div>
        <div class="lang-bar-wrap">
          <div style="flex:42;background:#f1e05a"></div>
          <div style="flex:25;background:#e34c26"></div>
          <div style="flex:18;background:#3572A5"></div>
          <div style="flex:10;background:#b07219"></div>
          <div style="flex:5;background:#555555"></div>
        </div>
        <div class="lang-row">
          <div class="lang-dot"><span style="background:#f1e05a"></span>JavaScript 42%</div>
          <div class="lang-dot"><span style="background:#e34c26"></span>HTML 25%</div>
          <div class="lang-dot"><span style="background:#3572A5"></span>Python 18%</div>
          <div class="lang-dot"><span style="background:#b07219"></span>Java 10%</div>
          <div class="lang-dot"><span style="background:#555555"></span>C/C++ 5%</div>
        </div>
      </div>
    </div>

    <!-- ACTIVITY GRAPH -->
    <div style="margin-top:12px">
      <div class="activity-wrap">
        <div style="font-size:11px;color:var(--muted);margin-bottom:10px;letter-spacing:0.06em;text-transform:uppercase">Contribution Activity</div>
        <div class="activity-grid" id="actGrid"></div>
        <div class="activity-labels">
          <span>Mar 2025</span><span>May 2025</span><span>Jul 2025</span><span>Sep 2025</span><span>Nov 2025</span><span>Today</span>
        </div>
      </div>
    </div>
  </div>

  <!-- TECH STACK -->
  <div class="section stack-section">
    <div class="section-header"><span>ls tech_stack/</span></div>
    <div class="terminal-box">
      <div class="terminal-bar"><div class="tb tb-r"></div><div class="tb tb-y"></div><div class="tb tb-g"></div></div>
      <div class="terminal-content">
        <div class="sub-title">⬡ Languages</div>
        <div class="badges">
          <div class="badge"><span class="badge-dot" style="background:#f1e05a"></span>JavaScript</div>
          <div class="badge"><span class="badge-dot" style="background:#3776ab"></span>Python</div>
          <div class="badge"><span class="badge-dot" style="background:#ed8b00"></span>Java</div>
          <div class="badge"><span class="badge-dot" style="background:#00599c"></span>C</div>
          <div class="badge"><span class="badge-dot" style="background:#004482"></span>C++</div>
          <div class="badge"><span class="badge-dot" style="background:#e34f26"></span>HTML5</div>
          <div class="badge"><span class="badge-dot" style="background:#1572b6"></span>CSS3</div>
        </div>
        <div class="sub-title" style="margin-top:18px">⚙️ Frameworks & Databases</div>
        <div class="badges">
          <div class="badge"><span class="badge-dot" style="background:#61dafb"></span>React</div>
          <div class="badge"><span class="badge-dot" style="background:#339933"></span>Node.js</div>
          <div class="badge"><span class="badge-dot" style="background:#888"></span>Express.js</div>
          <div class="badge"><span class="badge-dot" style="background:#13aa52"></span>MongoDB</div>
          <div class="badge"><span class="badge-dot" style="background:#4479a1"></span>MySQL</div>
          <div class="badge"><span class="badge-dot" style="background:#07405e"></span>SQLite</div>
        </div>
        <div class="sub-title" style="margin-top:18px">🛠 Tools</div>
        <div class="badges">
          <div class="badge"><span class="badge-dot" style="background:#f05032"></span>Git</div>
          <div class="badge"><span class="badge-dot" style="background:#fff"></span>GitHub</div>
          <div class="badge"><span class="badge-dot" style="background:#007acc"></span>VS Code</div>
          <div class="badge"><span class="badge-dot" style="background:#fcc624"></span>Linux</div>
          <div class="badge"><span class="badge-dot" style="background:#f24e1e"></span>Figma</div>
          <div class="badge"><span class="badge-dot" style="background:#00c4cc"></span>Canva</div>
        </div>
      </div>
    </div>
  </div>

  <!-- PROJECTS -->
  <div class="section">
    <div class="section-header"><span>cat projects/featured.md</span></div>
    <div class="projects-grid">
      <div class="project-card">
        <div class="proj-title">🔹 TaskFlow – Smart Task Management</div>
        <div class="proj-desc">Full-stack MERN task management app with authentication, protected routes, and a modern responsive UI.</div>
        <div class="proj-features">
          <div class="proj-feat">JWT Authentication & Protected Routes</div>
          <div class="proj-feat">Full CRUD task operations</div>
          <div class="proj-feat">Priority & Status Filtering</div>
          <div class="proj-feat">Clean responsive UI</div>
        </div>
        <div class="proj-badges">
          <span class="proj-badge">React</span>
          <span class="proj-badge">Node.js</span>
          <span class="proj-badge">MongoDB</span>
          <span class="proj-badge">JWT</span>
        </div>
      </div>
      <div class="project-card">
        <div class="proj-title">🔹 Food Order System</div>
        <div class="proj-desc">Full-stack group project for food ordering, user management, and admin functionality with database integration.</div>
        <div class="proj-features">
          <div class="proj-feat">User Management System</div>
          <div class="proj-feat">Food Ordering Workflow</div>
          <div class="proj-feat">Admin Dashboard</div>
          <div class="proj-feat">Full Frontend–Backend Integration</div>
        </div>
        <div class="proj-badges">
          <span class="proj-badge">Express.js</span>
          <span class="proj-badge">MySQL</span>
          <span class="proj-badge">JavaScript</span>
        </div>
      </div>
    </div>
  </div>

  <!-- GOALS -->
  <div class="section">
    <div class="section-header"><span>cat goals_2026.txt</span></div>
    <div class="goals-list">
      <div class="goal-row"><span class="goal-icon">✦</span>Build more real-world full stack portfolio projects</div>
      <div class="goal-row"><span class="goal-icon">✦</span>Land a Software Engineering internship</div>
      <div class="goal-row"><span class="goal-icon">✦</span>Master backend architecture & database design</div>
      <div class="goal-row"><span class="goal-icon">✦</span>Contribute actively to open source on GitHub</div>
      <div class="goal-row"><span class="goal-icon">✦</span>Improve UI/UX design skills</div>
      <div class="goal-row"><span class="goal-icon">✦</span>Grow as a professional software engineer</div>
    </div>
  </div>

  <!-- CONTACT -->
  <div class="section">
    <div class="contact-bar">
      <span>📍 Sri Lanka</span>
      <span class="sep">·</span>
      <a href="mailto:deneshkar015@gmail.com" style="color:var(--blue)">deneshkar015@gmail.com</a>
      <span class="sep">·</span>
      <span>🟢 Open to Opportunities</span>
    </div>
  </div>

  <div class="footer">
    <div style="font-style:italic;color:var(--muted);margin-bottom:8px">"I enjoy learning by building. I like turning ideas into useful applications."</div>
    <div>Built with pure HTML · No external image dependencies · Works everywhere</div>
  </div>
</div>

<script>
// Generate contribution activity graph
const grid = document.getElementById('actGrid');
const levels = [0,0,0,0,1,0,0,0,0,0,0,0,0,0,0,0,1,0,0,0,1,0,0,0,0,0,0,0,0,0,0,1,1,0,0,0,0,0,0,0,0,0,0,0,1,0,0,0,0,0,0,0,0,1,1,1,0,0,0,0,0,0,1,0,0,0,0,0,1,0,0,0,0,0,0,0,0,0,0,0,0,0,1,0,0,0,0,0,0,1,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,1,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,1,0,0,0,0,0,0,0,1,0,0,0,0,0,0,0,0,0,0,0,1,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0];
const weeks = Math.ceil(levels.length / 7);
for(let w=0;w<weeks;w++){
  const col = document.createElement('div');
  col.className='activity-col';
  for(let d=0;d<7;d++){
    const idx=w*7+d;
    const cell=document.createElement('div');
    cell.className='activity-cell act-'+(idx<levels.length?levels[idx]:0);
    col.appendChild(cell);
  }
  grid.appendChild(col);
}
</script>
</body>
</html>
