<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<title>Roberto Carlos — Profile</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500;700;800&display=swap" rel="stylesheet">
<style>
  :root{
    --bg:#070a14;
    --panel:#0d1220;
    --panel-2:#0a0e1a;
    --border:#1c2438;
    --cyan:#3ddcf7;
    --purple:#a78bfa;
    --green:#22e584;
    --text:#c9d3e8;
    --text-dim:#5f6c8a;
    --mono:'JetBrains Mono', monospace;
  }
  *{box-sizing:border-box;}
  body{
    margin:0;
    background:
      radial-gradient(circle at 15% 0%, rgba(61,220,247,0.06), transparent 40%),
      radial-gradient(circle at 85% 10%, rgba(167,139,250,0.06), transparent 40%),
      var(--bg);
    font-family: var(--mono);
    color: var(--text);
    padding: 32px 16px;
  }
  .wrap{ max-width: 1040px; margin: 0 auto; display:flex; flex-direction:column; gap:20px; }

  /* mac window chrome */
  .win{
    background: var(--panel);
    border: 1px solid var(--border);
    border-radius: 10px;
    overflow: hidden;
    box-shadow: 0 0 0 1px rgba(61,220,247,0.03), 0 12px 28px rgba(0,0,0,0.35);
  }
  .win-bar{
    display:flex; align-items:center; gap:8px;
    padding: 9px 12px;
    background: var(--panel-2);
    border-bottom: 1px solid var(--border);
  }
  .dot{ width:10px; height:10px; border-radius:50%; }
  .dot.r{ background:#ff5f56; }
  .dot.y{ background:#ffbd2e; }
  .dot.g{ background:#27c93f; }
  .win-title{
    margin-left: 8px;
    font-size: 12px;
    color: var(--text-dim);
    letter-spacing: 0.02em;
  }
  .win-body{ padding: 20px 22px; }

  /* header */
  .header{ display:flex; align-items:center; gap:22px; flex-wrap: wrap; padding: 22px; }
  .avatar{
    width: 92px; height: 92px; border-radius: 50%;
    border: 2px solid var(--cyan);
    box-shadow: 0 0 22px rgba(61,220,247,0.35);
    display:flex; align-items:center; justify-content:center;
    background: linear-gradient(160deg,#101a2e,#0a0e1a);
    font-size: 30px; font-weight:800; color: var(--cyan);
    flex-shrink:0;
  }
  .htext{ flex:1; min-width:240px; }
  .name{ font-size: 26px; font-weight:800; color:#eaf6ff; letter-spacing:0.02em; margin:0; }
  .role{ font-size:13px; color: var(--cyan); margin:6px 0 4px; letter-spacing:0.03em; }
  .sub{ font-size:12px; color: var(--text-dim); margin:0 0 10px; }
  .loc{ font-size:12px; color:var(--text-dim); display:flex; align-items:center; gap:6px; margin-bottom:10px;}
  .badges{ display:flex; gap:10px; align-items:center; flex-wrap:wrap; }
  .online{
    font-size:11px; color:var(--green); border:1px solid var(--green);
    padding:3px 10px; border-radius:20px; display:flex; align-items:center; gap:6px;
  }
  .online::before{ content:''; width:6px; height:6px; border-radius:50%; background:var(--green); box-shadow:0 0 8px var(--green); }
  .social{ font-size:12px; color:var(--text-dim); }
  .social b{ color: var(--text); }

  /* two-col */
  .cols{ display:grid; grid-template-columns: 1fr 1fr; gap:20px; }
  @media (max-width: 760px){ .cols{ grid-template-columns: 1fr; } }

  .prompt{ color: var(--green); }
  .path{ color: var(--purple); }
  .cmd{ color: var(--cyan); }
  pre.term{ margin:0; white-space:pre-wrap; font-size:13px; line-height:1.7; color:var(--text); }
  .comment{ color:#4a5875; }

  .stat-row{ display:flex; gap:14px; }
  .stat{ flex:1; text-align:center; padding:14px 8px; background: var(--panel-2); border:1px solid var(--border); border-radius:8px; }
  .stat .num{ font-size:24px; font-weight:800; color:var(--cyan); }
  .stat .lbl{ font-size:11px; color:var(--text-dim); margin-top:4px; }

  .conn-row{ display:flex; align-items:center; gap:10px; padding:9px 0; border-bottom:1px solid var(--border); font-size:12px; }
  .conn-row:last-child{ border-bottom:none; }
  .conn-k{ color:var(--text-dim); width:70px; flex-shrink:0; }
  .conn-v{ color: var(--cyan); }

  /* tech grid - flat, as in real GitHub README */
  .tech-grid{
    display:flex; flex-wrap:wrap; gap:14px; justify-content:flex-start; align-items:center;
  }
  .tech-grid img{ width:42px; height:42px; }

  /* projects */
  .proj-grid{ display:grid; grid-template-columns: repeat(3, 1fr); gap:16px; }
  @media (max-width:760px){ .proj-grid{ grid-template-columns:1fr; } }
  .proj-title{ font-size:14px; color:#eaf6ff; margin:0 0 6px; }
  .proj-desc{ font-size:11.5px; color:var(--text-dim); line-height:1.5; margin:0 0 10px; }
  .tag{ display:inline-block; font-size:10px; color:var(--purple); border:1px solid var(--purple); border-radius:5px; padding:2px 7px; margin:0 6px 6px 0; }
  .link{ font-size:12px; color:var(--cyan); text-decoration:none; }

  /* timeline */
  .tl{ list-style:none; margin:0; padding:0; border-left:2px solid var(--border); }
  .tl li{ position:relative; padding:0 0 18px 20px; }
  .tl li:last-child{ padding-bottom:0; }
  .tl li::before{ content:''; position:absolute; left:-7px; top:2px; width:11px; height:11px; border-radius:50%; background:var(--panel); border:2px solid var(--cyan); }
  .tl-year{ font-size:13px; font-weight:700; color:#eaf6ff; }
  .tl-title{ font-size:12px; color:var(--purple); margin:2px 0; }
  .tl-desc{ font-size:11.5px; color:var(--text-dim); }

  footer{ text-align:center; font-size:12px; color:var(--text-dim); padding: 8px 0 0; }
  footer .prompt{ color:var(--green); }
</style>
</head>
<body>
<div class="wrap">

  <!-- header -->
  <div class="win">
    <div class="win-bar">
      <span class="dot r"></span><span class="dot y"></span><span class="dot g"></span>
      <span class="win-title">~/roberto-carlos — zsh</span>
    </div>
    <div class="header">
      <div class="avatar">RC</div>
      <div class="htext">
        <p class="name">ROBERTO CARLOS</p>
        <p class="role">FULL STACK DEVELOPER</p>
        <p class="sub">IOT ENGINEER · AI ENTHUSIAST · NETWORKS</p>
        <p class="loc">📍 Guayaquil, Ecuador</p>
        <div class="badges">
          <span class="online">online</span>
          <span class="social">gh <b>@Robert-29</b></span>
          <span class="social">x <b>@Roberto53713354</b></span>
        </div>
      </div>
    </div>
  </div>

  <!-- about + stats -->
  <div class="cols">
    <div class="win">
      <div class="win-bar">
        <span class="dot r"></span><span class="dot y"></span><span class="dot g"></span>
        <span class="win-title">about.me — bash</span>
      </div>
      <div class="win-body">
        <pre class="term"><span class="prompt">C:\Users\Roberto&gt;</span> <span class="cmd">whoami</span>
Roberto Carlos

<span class="prompt">C:\Users\Roberto&gt;</span> <span class="cmd">cat</span> about.txt
Desarrollador Full-Stack apasionado por construir
sistemas completos e inteligentes.
Me especializo en desarrollo web, sistemas
embebidos, IoT y soluciones de IA aplicadas
al mundo real.

<span class="prompt">C:\Users\Roberto&gt;</span> <span class="cmd">skills</span> --list
<span class="comment">[✓]</span> Problem Solver
<span class="comment">[✓]</span> Clean Code
<span class="comment">[✓]</span> Continuous Learner
<span class="comment">[✓]</span> Coffee Powered

<span class="prompt">C:\Users\Roberto&gt;</span> <span class="cmd">_</span></pre>
      </div>
    </div>

    <div style="display:flex; flex-direction:column; gap:20px;">
      <div class="win">
        <div class="win-bar">
          <span class="dot r"></span><span class="dot y"></span><span class="dot g"></span>
          <span class="win-title">github.stats — sh</span>
        </div>
        <div class="win-body">
          <div class="stat-row">
            <div class="stat"><div class="num">165</div><div class="lbl">Total Contributions</div></div>
            <div class="stat"><div class="num">1</div><div class="lbl">Current Streak</div></div>
            <div class="stat"><div class="num">15</div><div class="lbl">Longest Streak</div></div>
          </div>
        </div>
      </div>

      <div class="win">
        <div class="win-bar">
          <span class="dot r"></span><span class="dot y"></span><span class="dot g"></span>
          <span class="win-title">connect.sh</span>
        </div>
        <div class="win-body">
          <div class="conn-row"><span class="conn-k">GitHub</span><span class="conn-v">github.com/Robert-29</span></div>
          <div class="conn-row"><span class="conn-k">Email</span><span class="conn-v">robertocarlos.dev@gmail.com</span></div>
          <div class="conn-row"><span class="conn-k">Location</span><span class="conn-v">Guayaquil, Ecuador</span></div>
        </div>
      </div>
    </div>
  </div>

  <!-- tech stack: flat grid, same collection as the real GitHub README -->
  <div class="win">
    <div class="win-bar">
      <span class="dot r"></span><span class="dot y"></span><span class="dot g"></span>
      <span class="win-title">tech.stack — ls -la</span>
    </div>
    <div class="win-body">
      <div class="tech-grid">
        <img title="HTML5" src="https://cdn.jsdelivr.net/gh/devicon/devicon/icons/html5/html5-original.svg">
        <img title="CSS3" src="https://cdn.jsdelivr.net/gh/devicon/devicon/icons/css3/css3-original.svg">
        <img title="JavaScript" src="https://cdn.jsdelivr.net/gh/devicon/devicon/icons/javascript/javascript-original.svg">
        <img title="React" src="https://cdn.jsdelivr.net/gh/devicon/devicon/icons/react/react-original.svg">
        <img title="Vite" src="https://cdn.jsdelivr.net/gh/devicon/devicon/icons/vitejs/vitejs-original.svg">
        <img title="Tailwind CSS" src="https://cdn.jsdelivr.net/gh/devicon/devicon/icons/tailwindcss/tailwindcss-original.svg">
        <img title="TypeScript" src="https://cdn.jsdelivr.net/gh/devicon/devicon/icons/typescript/typescript-original.svg">
        <img title="Node.js" src="https://cdn.jsdelivr.net/gh/devicon/devicon/icons/nodejs/nodejs-original.svg">
        <img title="Express" src="https://cdn.jsdelivr.net/gh/devicon/devicon/icons/express/express-original.svg" style="filter:invert(1);">
        <img title="npm" src="https://cdn.jsdelivr.net/gh/devicon/devicon/icons/npm/npm-original-wordmark.svg">
        <img title="Python" src="https://cdn.jsdelivr.net/gh/devicon/devicon/icons/python/python-original.svg">
        <img title="Java" src="https://cdn.jsdelivr.net/gh/devicon/devicon/icons/java/java-original.svg">
        <img title="PostgreSQL" src="https://cdn.jsdelivr.net/gh/devicon/devicon/icons/postgresql/postgresql-original.svg">
        <img title="Supabase" src="https://cdn.jsdelivr.net/gh/devicon/devicon/icons/supabase/supabase-original.svg">
        <img title="SQLite" src="https://cdn.jsdelivr.net/gh/devicon/devicon/icons/sqlite/sqlite-original.svg">
        <img title="Redis" src="https://cdn.jsdelivr.net/gh/devicon/devicon/icons/redis/redis-original.svg">
        <img title="Prisma" src="https://cdn.jsdelivr.net/gh/devicon/devicon/icons/prisma/prisma-original.svg" style="filter:invert(1);">
        <img title="Arduino" src="https://cdn.jsdelivr.net/gh/devicon/devicon/icons/arduino/arduino-original.svg">
        <img title="ESP32 / Espressif" src="https://cdn.jsdelivr.net/npm/simple-icons@latest/icons/espressif.svg" style="filter: invert(28%) sepia(89%) saturate(3000%) hue-rotate(340deg);">
        <img title="Blender / 3D" src="https://cdn.jsdelivr.net/gh/devicon/devicon/icons/blender/blender-original.svg">
        <img title="Ubuntu" src="https://cdn.jsdelivr.net/gh/devicon/devicon/icons/ubuntu/ubuntu-plain.svg">
        <img title="Linux" src="https://cdn.jsdelivr.net/gh/devicon/devicon/icons/linux/linux-original.svg" style="filter:invert(1);">
        <img title="Windows" src="https://cdn.jsdelivr.net/gh/devicon/devicon/icons/windows8/windows8-original.svg">
        <img title="Cisco" src="https://cdn.jsdelivr.net/npm/simple-icons@latest/icons/cisco.svg" style="filter: invert(60%) sepia(90%) saturate(2000%) hue-rotate(175deg);">
        <img title="Wireshark" src="https://cdn.jsdelivr.net/npm/simple-icons@latest/icons/wireshark.svg" style="filter: invert(75%) sepia(15%) saturate(700%) hue-rotate(160deg);">
      </div>
    </div>
  </div>

  <!-- projects -->
  <div class="win">
    <div class="win-bar">
      <span class="dot r"></span><span class="dot y"></span><span class="dot g"></span>
      <span class="win-title">featured.projects</span>
    </div>
    <div class="win-body">
      <div class="proj-grid">
        <div>
          <p class="proj-title">SIBIA</p>
          <p class="proj-desc">Sistema Inteligente de Bienestar e Inteligencia Académica. Plataforma full-stack universitaria con IA para detección de riesgo estudiantil.</p>
          <span class="tag">React</span><span class="tag">Node.js</span><span class="tag">PostgreSQL</span><span class="tag">AI</span>
          <div style="margin-top:8px;"><a class="link" href="#">Ver repositorio →</a></div>
        </div>
        <div>
          <p class="proj-title">Puente Levadizo IoT</p>
          <p class="proj-desc">Sistema automatizado con ESP32 y monitoreo en tiempo real. Control remoto con sensores y dashboard.</p>
          <span class="tag">ESP32</span><span class="tag">IoT</span><span class="tag">WebSockets</span>
          <div style="margin-top:8px;"><a class="link" href="#">Ver repositorio →</a></div>
        </div>
        <div>
          <p class="proj-title">Sistema de Reservaciones</p>
          <p class="proj-desc">Plataforma de reservas de hotel con panel administrativo, autenticación y gestión de habitaciones.</p>
          <span class="tag">React</span><span class="tag">Node.js</span><span class="tag">MySQL</span>
          <div style="margin-top:8px;"><a class="link" href="#">Ver repositorio →</a></div>
        </div>
      </div>
    </div>
  </div>

  <!-- timeline -->
  <div class="win">
    <div class="win-bar">
      <span class="dot r"></span><span class="dot y"></span><span class="dot g"></span>
      <span class="win-title">timeline.log</span>
    </div>
    <div class="win-body">
      <ul class="tl">
        <li><div class="tl-year">2022</div><div class="tl-title">Inicio del camino</div><div class="tl-desc">Primeros proyectos con Arduino y programación básica.</div></li>
        <li><div class="tl-year">2023</div><div class="tl-title">Desarrollo Web</div><div class="tl-desc">Descubrí el mundo web con JavaScript y React.</div></li>
        <li><div class="tl-year">2024</div><div class="tl-title">IoT y Redes</div><div class="tl-desc">Proyectos con ESP32, sensores y redes.</div></li>
        <li><div class="tl-year">2025</div><div class="tl-title">IA y Full Stack</div><div class="tl-desc">Construyendo sistemas inteligentes y escalables.</div></li>
        <li><div class="tl-year">Ahora</div><div class="tl-title">SIBIA y más</div><div class="tl-desc">Enfocado en impactar con tecnología.</div></li>
      </ul>
    </div>
  </div>

  <footer>
    <span class="prompt">$</span> echo "La tecnología es mejor cuando une a las personas."
  </footer>

</div>
</body>
</html>
