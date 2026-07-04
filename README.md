<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Lokender Chauhan — Full Stack Developer</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500;600;700;800&family=Inter:wght@400;500;600;700&display=swap');

  :root{
    --void:#0A0C10;
    --panel:#10141B;
    --panel-raised:#161B24;
    --border:#232A36;
    --border-soft:#1A2029;
    --accent:#FF6E96;
    --accent-2:#5EEAD4;
    --accent-3:#FFD166;
    --text-hi:#E8EAF0;
    --text-mid:#9AA3B2;
    --text-dim:#545C6B;
    --mono: 'JetBrains Mono', monospace;
    --sans: 'Inter', sans-serif;
  }

  *{ box-sizing:border-box; margin:0; padding:0; }

  html{ scroll-behavior:smooth; }

  body{
    background:var(--void);
    color:var(--text-hi);
    font-family:var(--sans);
    line-height:1.6;
    overflow-x:hidden;
    background-image:
      radial-gradient(ellipse 900px 500px at 15% -10%, rgba(255,110,150,0.08), transparent),
      radial-gradient(ellipse 700px 500px at 90% 20%, rgba(94,234,212,0.06), transparent);
  }

  ::selection{ background:var(--accent); color:var(--void); }

  a{ color:inherit; text-decoration:none; }

  /* ---------- Editor chrome ---------- */
  .editor{
    max-width:1180px;
    margin:32px auto;
    border:1px solid var(--border);
    border-radius:14px;
    overflow:hidden;
    background:var(--panel);
    box-shadow:0 40px 100px -30px rgba(0,0,0,0.7);
  }

  .titlebar{
    display:flex;
    align-items:center;
    gap:14px;
    padding:14px 20px;
    background:var(--panel-raised);
    border-bottom:1px solid var(--border);
  }
  .dots{ display:flex; gap:8px; }
  .dot{ width:12px; height:12px; border-radius:50%; }
  .dot.r{ background:#FF5F57; }
  .dot.y{ background:#FEBC2E; }
  .dot.g{ background:#28C840; }

  .tab{
    font-family:var(--mono);
    font-size:12.5px;
    color:var(--text-mid);
    background:var(--panel);
    border:1px solid var(--border-soft);
    border-bottom:none;
    padding:6px 14px;
    border-radius:8px 8px 0 0;
    display:flex;
    align-items:center;
    gap:8px;
  }
  .tab::before{ content:'●'; color:var(--accent); font-size:8px; }

  .body-wrap{
    display:flex;
  }

  .gutter{
    flex:0 0 auto;
    padding:40px 0;
    text-align:right;
    color:var(--text-dim);
    font-family:var(--mono);
    font-size:12px;
    user-select:none;
    background:linear-gradient(180deg, transparent, rgba(255,255,255,0.01));
    border-right:1px solid var(--border-soft);
  }
  .gutter span{
    display:block;
    height:28px;
    line-height:28px;
    padding:0 14px 0 20px;
  }

  .content{
    flex:1;
    min-width:0;
    padding:40px 44px 60px;
  }

  @media (max-width:720px){
    .gutter{ display:none; }
    .content{ padding:32px 20px 48px; }
    .editor{ margin:16px; border-radius:10px; }
  }

  .comment{ color:var(--text-dim); font-family:var(--mono); font-size:13px; }
  .kw{ color:var(--accent-2); }
  .str{ color:var(--accent-3); }
  .fn{ color:var(--accent); }

  /* ---------- Hero ---------- */
  .hero{ padding:24px 0 48px; }
  .eyebrow{
    font-family:var(--mono);
    font-size:13px;
    color:var(--text-dim);
    margin-bottom:14px;
  }
  h1{
    font-family:var(--mono);
    font-size:clamp(28px, 5vw, 46px);
    font-weight:800;
    letter-spacing:-0.02em;
    line-height:1.15;
  }
  h1 .name{ color:var(--text-hi); }
  h1 .accent{ color:var(--accent); }

  .role-line{
    margin-top:14px;
    font-family:var(--mono);
    font-size:clamp(14px, 2.4vw, 18px);
    color:var(--accent-2);
    min-height:1.6em;
  }
  .role-line .cursor{
    display:inline-block;
    width:9px; height:1.1em;
    background:var(--accent);
    margin-left:2px;
    vertical-align:middle;
    animation:blink 1s steps(1) infinite;
  }
  @keyframes blink{ 50%{ opacity:0; } }

  .hero-sub{
    margin-top:20px;
    max-width:560px;
    color:var(--text-mid);
    font-size:15.5px;
  }

  .hero-cta{
    margin-top:28px;
    display:flex;
    gap:12px;
    flex-wrap:wrap;
  }
  .btn{
    font-family:var(--mono);
    font-size:13px;
    padding:11px 20px;
    border-radius:8px;
    border:1px solid var(--border);
    display:inline-flex;
    align-items:center;
    gap:8px;
    transition:transform .25s ease, border-color .25s ease, background .25s ease;
  }
  .btn.primary{
    background:var(--accent);
    color:var(--void);
    border-color:var(--accent);
    font-weight:600;
  }
  .btn.primary:hover{ transform:translateY(-2px); box-shadow:0 12px 24px -10px rgba(255,110,150,0.5); }
  .btn.ghost:hover{ border-color:var(--accent-2); color:var(--accent-2); transform:translateY(-2px); }

  /* ---------- Section headers ---------- */
  .section{ padding:46px 0; border-top:1px dashed var(--border-soft); }
  .section:first-of-type{ border-top:none; }
  .sec-head{
    display:flex;
    align-items:baseline;
    gap:10px;
    margin-bottom:26px;
    flex-wrap:wrap;
  }
  .sec-tag{
    font-family:var(--mono);
    font-size:12px;
    color:var(--text-dim);
  }
  .sec-title{
    font-family:var(--mono);
    font-size:22px;
    font-weight:700;
  }
  .sec-title .fn{ font-weight:700; }

  /* ---------- Stack strip ---------- */
  .stack-row{
    display:flex;
    gap:10px;
    flex-wrap:wrap;
  }
  .chip{
    font-family:var(--mono);
    font-size:12.5px;
    padding:8px 13px;
    border:1px solid var(--border);
    border-radius:7px;
    color:var(--text-mid);
    background:var(--panel-raised);
    transition:all .2s ease;
  }
  .chip:hover{ color:var(--accent-2); border-color:var(--accent-2); transform:translateY(-2px); }

  .lang-card{
    margin-top:22px;
    border:1px solid var(--border);
    border-radius:10px;
    overflow:hidden;
    background:var(--panel-raised);
  }
  .lang-card img{ display:block; width:100%; height:auto; }

  /* ---------- 3D Project cards ---------- */
  .stage{ perspective:1400px; }
  .projects{
    display:grid;
    grid-template-columns:repeat(2, 1fr);
    gap:22px;
  }
  @media (max-width:720px){ .projects{ grid-template-columns:1fr; } }

  .card3d{
    position:relative;
    border:1px solid var(--border);
    background:linear-gradient(160deg, var(--panel-raised), var(--panel));
    border-radius:12px;
    padding:26px;
    transform-style:preserve-3d;
    transition:transform .12s ease, box-shadow .3s ease, border-color .3s ease;
    will-change:transform;
  }
  .card3d:hover{ border-color:var(--accent); box-shadow:0 30px 60px -25px rgba(255,110,150,0.35); }
  .card3d .glow{
    position:absolute; inset:0;
    border-radius:12px;
    background:radial-gradient(280px circle at var(--mx,50%) var(--my,50%), rgba(255,110,150,0.14), transparent 60%);
    opacity:0; transition:opacity .3s ease;
    pointer-events:none;
  }
  .card3d:hover .glow{ opacity:1; }

  .card-top{
    display:flex;
    justify-content:space-between;
    align-items:center;
    margin-bottom:16px;
    font-family:var(--mono);
    font-size:11.5px;
    color:var(--text-dim);
  }
  .card-top .ext{
    color:var(--void);
    background:var(--accent-2);
    padding:2px 8px;
    border-radius:5px;
    font-weight:700;
  }
  .card-name{
    font-family:var(--mono);
    font-size:19px;
    font-weight:700;
    margin-bottom:8px;
  }
  .card-desc{ color:var(--text-mid); font-size:14px; margin-bottom:16px; }
  .card-meta{
    display:flex;
    gap:8px;
    flex-wrap:wrap;
    margin-bottom:18px;
  }
  .card-meta span{
    font-family:var(--mono);
    font-size:11px;
    color:var(--accent-3);
    background:rgba(255,209,102,0.08);
    border:1px solid rgba(255,209,102,0.25);
    padding:3px 8px;
    border-radius:5px;
  }
  .card-link{
    font-family:var(--mono);
    font-size:13px;
    color:var(--accent);
    display:inline-flex;
    align-items:center;
    gap:6px;
    font-weight:600;
  }
  .card-link:hover{ color:var(--accent-2); }

  /* ---------- Writing ---------- */
  .write-card{
    border:1px solid var(--border);
    border-radius:10px;
    padding:24px;
    background:var(--panel-raised);
  }
  .write-card h3{
    font-family:var(--mono);
    font-size:17px;
    margin-bottom:8px;
  }
  .write-card p{ color:var(--text-mid); font-size:14px; margin-bottom:14px; }

  /* ---------- Stats ---------- */
  .stats{
    display:grid;
    grid-template-columns:repeat(3,1fr);
    gap:16px;
  }
  @media (max-width:600px){ .stats{ grid-template-columns:1fr; } }
  .stat{
    border:1px solid var(--border);
    border-radius:10px;
    padding:22px;
    text-align:center;
    background:var(--panel-raised);
  }
  .stat .num{
    font-family:var(--mono);
    font-size:30px;
    font-weight:800;
    color:var(--accent);
  }
  .stat .lbl{
    margin-top:6px;
    font-size:12.5px;
    color:var(--text-mid);
    font-family:var(--mono);
  }

  /* ---------- GitHub perf images ---------- */
  .perf-grid{
    display:grid;
    grid-template-columns:1fr 1fr;
    gap:18px;
  }
  @media (max-width:720px){ .perf-grid{ grid-template-columns:1fr; } }
  .perf-grid img{
    width:100%;
    border-radius:10px;
    border:1px solid var(--border);
  }

  /* ---------- Contact ---------- */
  .connect{
    display:flex;
    gap:12px;
    flex-wrap:wrap;
  }

  footer{
    text-align:center;
    padding:36px 20px 44px;
    color:var(--text-dim);
    font-family:var(--mono);
    font-size:12.5px;
  }
  footer .quote{
    color:var(--text-mid);
    font-size:14px;
    margin-bottom:10px;
    font-style:italic;
  }
</style>
</head>
<body>

<div class="editor">
  <div class="titlebar">
    <div class="dots">
      <span class="dot r"></span><span class="dot y"></span><span class="dot g"></span>
    </div>
    <div class="tab">lokender-chauhan.dev</div>
  </div>

  <div class="body-wrap">
    <div class="gutter" id="gutter"></div>

    <div class="content">

      <!-- HERO -->
      <section class="hero">
        <div class="eyebrow"><span class="comment">// portfolio.init()</span></div>
        <h1><span class="kw">const</span> <span class="name">developer</span> = <span class="str">"Lokender Chauhan"</span><span class="accent">;</span></h1>
        <div class="role-line" id="typed"></div>
        <p class="hero-sub">Full stack developer building scalable web apps, SaaS products, and AI-driven automation — clean UI on top of optimized, dependable backends.</p>
        <div class="hero-cta">
          <a class="btn primary" href="https://lokender-portfolio.vercel.app/" target="_blank" rel="noopener">View Portfolio ↗</a>
          <a class="btn ghost" href="mailto:slokender05@gmail.com">Email Me</a>
        </div>
      </section>

      <!-- STACK -->
      <section class="section" id="stack">
        <div class="sec-head">
          <span class="sec-tag">01</span>
          <span class="sec-title"><span class="fn">techStack</span>()</span>
        </div>
        <div class="stack-row">
          <span class="chip">HTML5</span><span class="chip">CSS3</span><span class="chip">JavaScript</span>
          <span class="chip">TypeScript</span><span class="chip">React</span><span class="chip">Next.js</span>
          <span class="chip">Node.js</span><span class="chip">Express</span><span class="chip">MongoDB</span>
          <span class="chip">Tailwind</span><span class="chip">Git</span><span class="chip">Docker</span>
          <span class="chip">Vercel</span>
        </div>
        <div class="lang-card">
          <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=lokender-droid&layout=compact&theme=tokyonight&hide_border=true&bg_color=161B24&title_color=FF6E96&text_color=9AA3B2" alt="Top languages" loading="lazy">
        </div>
      </section>

      <!-- PROJECTS -->
      <section class="section stage" id="projects">
        <div class="sec-head">
          <span class="sec-tag">02</span>
          <span class="sec-title"><span class="fn">featuredProjects</span>()</span>
        </div>
        <div class="projects">

          <div class="card3d" data-tilt>
            <div class="glow"></div>
            <div class="card-top"><span>project/portfolio</span><span class="ext">.TSX</span></div>
            <div class="card-name">Portfolio Website</div>
            <p class="card-desc">Personal brand & showcase platform built for performance and clean, fast-loading UI.</p>
            <div class="card-meta"><span>React</span><span>Tailwind</span><span>Vercel</span><span>SEO</span></div>
            <a class="card-link" href="https://lokender-portfolio.vercel.app/" target="_blank" rel="noopener">Live Preview ↗</a>
          </div>

          <div class="card3d" data-tilt>
            <div class="glow"></div>
            <div class="card-top"><span>project/dashboard-app</span><span class="ext">.JS</span></div>
            <div class="card-name">Analytics Dashboard App</div>
            <p class="card-desc">Full-stack data visualization system with authenticated user sessions and live charts.</p>
            <div class="card-meta"><span>MongoDB</span><span>Express</span><span>React</span><span>Node</span></div>
            <a class="card-link" href="https://github.com/lokender-droid/dashboard-app" target="_blank" rel="noopener">GitHub Repo ↗</a>
          </div>

        </div>
      </section>

      <!-- WRITING -->
      <section class="section" id="writing">
        <div class="sec-head">
          <span class="sec-tag">03</span>
          <span class="sec-title"><span class="fn">writing</span>()</span>
        </div>
        <div class="write-card">
          <h3>How to Build Fully Responsive Websites <span class="comment">(Production Level)</span></h3>
          <p>Technical write-ups on responsive design, performance optimization, and scalable frontend architecture.</p>
          <a class="card-link" href="https://medium.com/@lokender" target="_blank" rel="noopener">Read on Medium ↗</a>
        </div>
      </section>

      <!-- ACHIEVEMENTS -->
      <section class="section" id="achievements">
        <div class="sec-head">
          <span class="sec-tag">04</span>
          <span class="sec-title"><span class="fn">achievements</span>()</span>
        </div>
        <div class="stats">
          <div class="stat"><div class="num">50+</div><div class="lbl">Projects Delivered</div></div>
          <div class="stat"><div class="num">500+</div><div class="lbl">GitHub Contributions</div></div>
          <div class="stat"><div class="num">Full&nbsp;Stack</div><div class="lbl">+ SaaS Experience</div></div>
        </div>
      </section>

      <!-- GITHUB PERFORMANCE -->
      <section class="section" id="perf">
        <div class="sec-head">
          <span class="sec-tag">05</span>
          <span class="sec-title"><span class="fn">githubStats</span>()</span>
        </div>
        <div class="perf-grid">
          <img src="https://github-readme-stats.vercel.app/api?username=lokender-droid&show_icons=true&theme=tokyonight&hide_border=true&bg_color=161B24&title_color=FF6E96&text_color=9AA3B2" alt="GitHub stats" loading="lazy">
          <img src="https://github-readme-streak-stats.herokuapp.com/?user=lokender-droid&theme=tokyonight&hide_border=true&background=161B24&ring=FF6E96&fire=FF6E96&currStreakLabel=5EEAD4" alt="GitHub streak" loading="lazy">
        </div>
      </section>

      <!-- CONTACT -->
      <section class="section" id="contact">
        <div class="sec-head">
          <span class="sec-tag">06</span>
          <span class="sec-title"><span class="fn">connect</span>()</span>
        </div>
        <div class="connect">
          <a class="btn primary" href="mailto:slokender05@gmail.com">✉ Email</a>
          <a class="btn ghost" href="https://github.com/lokender-droid" target="_blank" rel="noopener">GitHub</a>
        </div>
      </section>

      <footer>
        <div class="quote">"I don't just write code — I engineer scalable systems."</div>
        <div>⭐ Star repositories if you find value · <span class="comment">// EOF</span></div>
      </footer>

    </div>
  </div>
</div>

<script>
  // Line-number gutter
  const gutter = document.getElementById('gutter');
  const lines = 60;
  for(let i=1;i<=lines;i++){
    const s = document.createElement('span');
    s.textContent = i;
    gutter.appendChild(s);
  }

  // Typing effect
  const roles = [
    "Building Scalable Web Apps",
    "SaaS & AI Driven Solutions",
    "Clean UI | Optimized Backend",
    "Automation First Mindset"
  ];
  const el = document.getElementById('typed');
  let ri=0, ci=0, deleting=false;
  function tick(){
    const full = roles[ri];
    if(!deleting){
      ci++;
      if(ci > full.length){ deleting = true; setTimeout(tick, 1200); return; }
    } else {
      ci--;
      if(ci < 0){ deleting=false; ri=(ri+1)%roles.length; ci=0; }
    }
    el.innerHTML = full.slice(0, ci) + '<span class="cursor"></span>';
    setTimeout(tick, deleting ? 35 : 55);
  }
  tick();

  // 3D tilt on project cards
  document.querySelectorAll('[data-tilt]').forEach(card=>{
    card.addEventListener('mousemove', (e)=>{
      const r = card.getBoundingClientRect();
      const x = e.clientX - r.left;
      const y = e.clientY - r.top;
      const rx = ((y / r.height) - 0.5) * -10;
      const ry = ((x / r.width) - 0.5) * 10;
      card.style.transform = `rotateX(${rx}deg) rotateY(${ry}deg) translateZ(6px)`;
      card.style.setProperty('--mx', x + 'px');
      card.style.setProperty('--my', y + 'px');
    });
    card.addEventListener('mouseleave', ()=>{
      card.style.transform = 'rotateX(0) rotateY(0) translateZ(0)';
    });
  });

  // Respect reduced motion
  if(window.matchMedia('(prefers-reduced-motion: reduce)').matches){
    document.querySelectorAll('[data-tilt]').forEach(c=> c.style.transition='none');
  }
</script>

</body>
</html>
