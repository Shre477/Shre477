<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Shreya Patra — Full Stack Developer</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet"/>
<style>
*{margin:0;padding:0;box-sizing:border-box}
:root{
  --bg:#0a0a0f;
  --bg2:#111118;
  --bg3:#16161f;
  --accent:#a855f7;
  --accent2:#7c3aed;
  --teal:#2dd4bf;
  --pink:#f472b6;
  --text:#e8e9f0;
  --muted:#8a8fa8;
  --border:#ffffff12;
  --card:#13131c;
}
html{scroll-behavior:smooth}
body{background:var(--bg);color:var(--text);font-family:'Space Grotesk',sans-serif;overflow-x:hidden}

/* CURSOR */
.cursor{width:10px;height:10px;background:var(--accent);border-radius:50%;position:fixed;pointer-events:none;z-index:9999;transition:transform .15s;mix-blend-mode:screen}
.cursor-ring{width:36px;height:36px;border:1px solid var(--accent);border-radius:50%;position:fixed;pointer-events:none;z-index:9998;transition:all .12s;opacity:.5}

/* NAV */
nav{position:fixed;top:0;width:100%;z-index:100;padding:1rem 2rem;display:flex;justify-content:space-between;align-items:center;border-bottom:1px solid var(--border);backdrop-filter:blur(20px);background:rgba(10,10,15,.7)}
.nav-logo{font-family:'JetBrains Mono',monospace;color:var(--accent);font-size:.9rem;letter-spacing:.1em}
.nav-links{display:flex;gap:2rem}
.nav-links a{color:var(--muted);text-decoration:none;font-size:.85rem;letter-spacing:.05em;transition:color .2s;text-transform:uppercase}
.nav-links a:hover{color:var(--accent)}
.nav-cta{background:var(--accent);color:#fff;padding:.45rem 1.2rem;border-radius:6px;text-decoration:none;font-size:.82rem;font-weight:600;transition:all .2s}
.nav-cta:hover{background:var(--accent2);transform:translateY(-1px)}

/* HERO */
#hero{min-height:100vh;display:flex;align-items:center;justify-content:center;text-align:center;padding:6rem 2rem 4rem;position:relative;overflow:hidden}
.hero-grid{position:absolute;inset:0;background-image:linear-gradient(var(--border) 1px,transparent 1px),linear-gradient(90deg,var(--border) 1px,transparent 1px);background-size:60px 60px;opacity:.4}
.hero-glow{position:absolute;top:20%;left:50%;transform:translateX(-50%);width:600px;height:600px;background:radial-gradient(circle,rgba(168,85,247,.15) 0%,transparent 70%);pointer-events:none}
.hero-content{position:relative;z-index:1}
.hero-tag{display:inline-block;border:1px solid var(--accent);color:var(--accent);padding:.3rem 1rem;border-radius:100px;font-size:.75rem;letter-spacing:.12em;text-transform:uppercase;margin-bottom:1.5rem;font-family:'JetBrains Mono',monospace}
h1{font-size:clamp(2.8rem,7vw,5.5rem);font-weight:700;line-height:1.05;margin-bottom:1.5rem;letter-spacing:-.02em}
h1 .name-accent{background:linear-gradient(135deg,var(--accent),var(--teal));-webkit-background-clip:text;-webkit-text-fill-color:transparent}
.hero-sub{font-size:1.1rem;color:var(--muted);max-width:540px;margin:0 auto 2.5rem;line-height:1.7}
.hero-btns{display:flex;gap:1rem;justify-content:center;flex-wrap:wrap}
.btn-primary{background:var(--accent);color:#fff;padding:.75rem 2rem;border-radius:8px;text-decoration:none;font-weight:600;font-size:.9rem;transition:all .2s;display:inline-flex;align-items:center;gap:.5rem}
.btn-primary:hover{background:var(--accent2);transform:translateY(-2px);box-shadow:0 8px 25px rgba(168,85,247,.3)}
.btn-outline{border:1px solid var(--border);color:var(--text);padding:.75rem 2rem;border-radius:8px;text-decoration:none;font-weight:500;font-size:.9rem;transition:all .2s}
.btn-outline:hover{border-color:var(--accent);color:var(--accent);transform:translateY(-2px)}
.scroll-hint{position:absolute;bottom:2rem;left:50%;transform:translateX(-50%);display:flex;flex-direction:column;align-items:center;gap:.5rem;color:var(--muted);font-size:.75rem}
.scroll-arrow{width:1px;height:40px;background:linear-gradient(var(--accent),transparent);animation:scrollpulse 2s infinite}
@keyframes scrollpulse{0%,100%{opacity:.3;transform:scaleY(.8)}50%{opacity:1;transform:scaleY(1)}}

/* SECTIONS */
section{padding:6rem 2rem}
.container{max-width:1100px;margin:0 auto}
.section-label{font-family:'JetBrains Mono',monospace;color:var(--accent);font-size:.75rem;letter-spacing:.2em;text-transform:uppercase;margin-bottom:.75rem;display:block}
.section-title{font-size:clamp(1.8rem,4vw,2.8rem);font-weight:700;margin-bottom:1rem;letter-spacing:-.02em}
.section-line{width:60px;height:3px;background:linear-gradient(var(--accent),var(--teal));border-radius:2px;margin-bottom:3rem}

/* ABOUT */
#about{background:var(--bg2)}
.about-grid{display:grid;grid-template-columns:1fr 1fr;gap:4rem;align-items:center}
.about-text p{color:var(--muted);line-height:1.8;margin-bottom:1rem;font-size:1rem}
.about-text p strong{color:var(--text)}
.about-stats{display:grid;grid-template-columns:1fr 1fr;gap:1rem}
.stat-card{background:var(--card);border:1px solid var(--border);border-radius:12px;padding:1.5rem;text-align:center;transition:all .2s}
.stat-card:hover{border-color:var(--accent);transform:translateY(-3px)}
.stat-num{font-size:2rem;font-weight:700;background:linear-gradient(135deg,var(--accent),var(--teal));-webkit-background-clip:text;-webkit-text-fill-color:transparent}
.stat-label{font-size:.8rem;color:var(--muted);margin-top:.25rem}

/* SKILLS */
#skills{background:var(--bg)}
.skills-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(280px,1fr));gap:1.5rem}
.skill-group{background:var(--card);border:1px solid var(--border);border-radius:16px;padding:1.75rem;transition:all .3s}
.skill-group:hover{border-color:var(--accent);transform:translateY(-4px);box-shadow:0 12px 40px rgba(168,85,247,.1)}
.skill-group-title{font-size:.8rem;letter-spacing:.15em;text-transform:uppercase;color:var(--accent);margin-bottom:1.25rem;font-family:'JetBrains Mono',monospace;display:flex;align-items:center;gap:.5rem}
.skill-group-title::before{content:'';display:inline-block;width:6px;height:6px;background:var(--accent);border-radius:50%}
.skill-tags{display:flex;flex-wrap:wrap;gap:.5rem}
.skill-tag{background:rgba(168,85,247,.08);border:1px solid rgba(168,85,247,.2);color:var(--text);padding:.3rem .75rem;border-radius:6px;font-size:.8rem;font-family:'JetBrains Mono',monospace;transition:all .2s}
.skill-tag:hover{background:rgba(168,85,247,.18);border-color:var(--accent)}

/* PROJECTS */
#projects{background:var(--bg2)}
.projects-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(320px,1fr));gap:1.5rem}
.project-card{background:var(--card);border:1px solid var(--border);border-radius:16px;padding:1.75rem;transition:all .3s;position:relative;overflow:hidden;cursor:pointer}
.project-card::before{content:'';position:absolute;top:0;left:0;right:0;height:2px;background:linear-gradient(90deg,var(--accent),var(--teal));transform:scaleX(0);transition:transform .3s;transform-origin:left}
.project-card:hover{border-color:rgba(168,85,247,.4);transform:translateY(-5px);box-shadow:0 16px 50px rgba(168,85,247,.12)}
.project-card:hover::before{transform:scaleX(1)}
.project-icon{font-size:2rem;margin-bottom:1rem}
.project-title{font-size:1.1rem;font-weight:600;margin-bottom:.5rem}
.project-desc{color:var(--muted);font-size:.87rem;line-height:1.65;margin-bottom:1.25rem}
.project-metrics{display:flex;gap:.5rem;flex-wrap:wrap;margin-bottom:1.25rem}
.metric{background:rgba(45,212,191,.08);border:1px solid rgba(45,212,191,.2);color:var(--teal);padding:.2rem .65rem;border-radius:4px;font-size:.73rem;font-family:'JetBrains Mono',monospace}
.project-tech{display:flex;flex-wrap:wrap;gap:.4rem;margin-bottom:1.25rem}
.tech-badge{background:rgba(255,255,255,.04);border:1px solid var(--border);color:var(--muted);padding:.2rem .6rem;border-radius:4px;font-size:.73rem}
.project-links{display:flex;gap:.75rem}
.project-link{color:var(--accent);text-decoration:none;font-size:.8rem;font-weight:500;display:flex;align-items:center;gap:.3rem;transition:color .2s}
.project-link:hover{color:var(--teal)}

/* DSA */
#dsa{background:var(--bg)}
.dsa-content{display:grid;grid-template-columns:1fr 1fr;gap:3rem;align-items:start}
.dsa-left p{color:var(--muted);line-height:1.8;margin-bottom:1.5rem}
.dsa-topics{display:flex;flex-direction:column;gap:.75rem}
.dsa-topic{display:flex;align-items:center;justify-content:space-between;background:var(--card);border:1px solid var(--border);border-radius:10px;padding:1rem 1.25rem;transition:all .2s}
.dsa-topic:hover{border-color:rgba(168,85,247,.3)}
.topic-name{font-size:.9rem;font-weight:500}
.topic-bar-wrap{width:120px;height:6px;background:var(--border);border-radius:3px;overflow:hidden}
.topic-bar{height:100%;border-radius:3px;background:linear-gradient(90deg,var(--accent),var(--teal));transition:width 1.5s cubic-bezier(.4,0,.2,1)}
.dsa-right{display:flex;flex-direction:column;gap:1rem}
.dsa-stat{background:var(--card);border:1px solid var(--border);border-radius:12px;padding:1.5rem;text-align:center;transition:all .2s}
.dsa-stat:hover{border-color:var(--accent);transform:translateY(-3px)}
.dsa-stat-num{font-size:2.2rem;font-weight:700;background:linear-gradient(135deg,var(--accent),var(--teal));-webkit-background-clip:text;-webkit-text-fill-color:transparent}
.dsa-stat-label{font-size:.8rem;color:var(--muted);margin-top:.3rem}
.dsa-link{display:inline-flex;align-items:center;gap:.5rem;background:rgba(255,165,22,.1);border:1px solid rgba(255,165,22,.3);color:#ffa516;padding:.75rem 1.5rem;border-radius:8px;text-decoration:none;font-size:.85rem;font-weight:600;margin-top:1rem;transition:all .2s}
.dsa-link:hover{background:rgba(255,165,22,.2);transform:translateY(-2px)}

/* EDUCATION */
#education{background:var(--bg2)}
.edu-timeline{position:relative;padding-left:2rem}
.edu-timeline::before{content:'';position:absolute;left:0;top:.5rem;bottom:.5rem;width:1px;background:linear-gradient(var(--accent),var(--teal))}
.edu-item{position:relative;margin-bottom:2.5rem;padding-left:1.5rem}
.edu-item::before{content:'';position:absolute;left:-2.35rem;top:.4rem;width:10px;height:10px;border-radius:50%;background:var(--accent);box-shadow:0 0 12px var(--accent)}
.edu-year{font-family:'JetBrains Mono',monospace;color:var(--accent);font-size:.75rem;letter-spacing:.1em;margin-bottom:.4rem}
.edu-degree{font-size:1.05rem;font-weight:600;margin-bottom:.3rem}
.edu-school{color:var(--muted);font-size:.9rem;margin-bottom:.3rem}
.edu-score{display:inline-block;background:rgba(45,212,191,.1);border:1px solid rgba(45,212,191,.2);color:var(--teal);padding:.2rem .75rem;border-radius:4px;font-size:.8rem;font-family:'JetBrains Mono',monospace}

/* CONTACT */
#contact{background:var(--bg);text-align:center}
.contact-inner{max-width:600px;margin:0 auto}
.contact-inner p{color:var(--muted);line-height:1.8;margin-bottom:2.5rem;font-size:1rem}
.contact-links{display:flex;gap:1rem;justify-content:center;flex-wrap:wrap;margin-bottom:2rem}
.contact-link{display:flex;align-items:center;gap:.5rem;background:var(--card);border:1px solid var(--border);color:var(--text);padding:.75rem 1.5rem;border-radius:10px;text-decoration:none;font-size:.85rem;font-weight:500;transition:all .2s}
.contact-link:hover{border-color:var(--accent);color:var(--accent);transform:translateY(-3px)}
.contact-email{font-family:'JetBrains Mono',monospace;color:var(--muted);font-size:.85rem}
.contact-email a{color:var(--accent);text-decoration:none}
.contact-email a:hover{color:var(--teal)}

/* FOOTER */
footer{background:var(--bg2);border-top:1px solid var(--border);padding:2rem;text-align:center;color:var(--muted);font-size:.82rem}
footer span{color:var(--accent)}

/* ANIMATIONS */
.fade-up{opacity:0;transform:translateY(30px);transition:all .7s cubic-bezier(.4,0,.2,1)}
.fade-up.visible{opacity:1;transform:translateY(0)}

/* MOBILE */
@media(max-width:768px){
  .about-grid,.dsa-content{grid-template-columns:1fr;gap:2rem}
  .nav-links{display:none}
  h1{font-size:2.4rem}
  .hero-btns{flex-direction:column;align-items:center}
}
</style>
</head>
<body>

<div class="cursor" id="cursor"></div>
<div class="cursor-ring" id="cursorRing"></div>

<nav>
  <span class="nav-logo">shreya.dev</span>
  <div class="nav-links">
    <a href="#about">About</a>
    <a href="#skills">Skills</a>
    <a href="#projects">Projects</a>
    <a href="#dsa">DSA</a>
    <a href="#education">Education</a>
    <a href="#contact">Contact</a>
  </div>
  <a href="mailto:Patrashreya477@gmail.com" class="nav-cta">Hire Me</a>
</nav>

<section id="hero">
  <div class="hero-grid"></div>
  <div class="hero-glow"></div>
  <div class="hero-content">
    <div class="hero-tag">Available for opportunities · May 2026</div>
    <h1>Hi, I'm <span class="name-accent">Shreya Patra</span><br/>Full Stack Developer</h1>
    <p class="hero-sub">CSE Final Year @ Dr. Sur Institute, Kolkata. I build end-to-end web applications with React, Node.js & MongoDB — with a focus on clean architecture and performance.</p>
    <div class="hero-btns">
      <a href="#projects" class="btn-primary">View Projects →</a>
      <a href="https://www.linkedin.com/in/shreya-p-737526301" target="_blank" class="btn-outline">LinkedIn</a>
      <a href="https://github.com/Shre477" target="_blank" class="btn-outline">GitHub</a>
    </div>
  </div>
  <div class="scroll-hint">
    <span>scroll</span>
    <div class="scroll-arrow"></div>
  </div>
</section>

<section id="about">
  <div class="container">
    <div class="about-grid fade-up">
      <div class="about-text">
        <span class="section-label">// about me</span>
        <h2 class="section-title">Building things<br/>that work well</h2>
        <div class="section-line"></div>
        <p>I'm a <strong>Full Stack Web Developer</strong> and final-year B.Tech CSE student passionate about building complete, production-ready web applications.</p>
        <p>From <strong>JWT-secured REST APIs</strong> to <strong>React Query-optimized frontends</strong>, I focus on the full picture — architecture decisions, performance, and clean code that scales.</p>
        <p>Currently seeking <strong>Full Stack Developer / SWE roles</strong> at product-based companies where I can contribute from day one.</p>
        <div style="margin-top:1.5rem;display:flex;gap:1rem;flex-wrap:wrap">
          <a href="https://github.com/Shre477" target="_blank" class="btn-primary" style="font-size:.82rem;padding:.5rem 1.2rem">GitHub Profile →</a>
          <a href="https://leetcode.com/u/shreya-patra-7005a1234/" target="_blank" class="btn-outline" style="font-size:.82rem;padding:.5rem 1.2rem">LeetCode →</a>
        </div>
      </div>
      <div class="about-stats">
        <div class="stat-card">
          <div class="stat-num">4+</div>
          <div class="stat-label">Projects Built</div>
        </div>
        <div class="stat-card">
          <div class="stat-num">60%</div>
          <div class="stat-label">API Call Reduction (React Query)</div>
        </div>
        <div class="stat-card">
          <div class="stat-num">92%</div>
          <div class="stat-label">Class XII Score</div>
        </div>
        <div class="stat-card">
          <div class="stat-num">2026</div>
          <div class="stat-label">Graduating May</div>
        </div>
      </div>
    </div>
  </div>
</section>

<section id="skills">
  <div class="container">
    <div class="fade-up">
      <span class="section-label">// tech stack</span>
      <h2 class="section-title">Skills & Tools</h2>
      <div class="section-line"></div>
    </div>
    <div class="skills-grid">
      <div class="skill-group fade-up">
        <div class="skill-group-title">Frontend</div>
        <div class="skill-tags">
          <span class="skill-tag">React.js</span>
          <span class="skill-tag">JavaScript ES6+</span>
          <span class="skill-tag">HTML5</span>
          <span class="skill-tag">CSS3</span>
          <span class="skill-tag">Tailwind CSS</span>
          <span class="skill-tag">Redux Toolkit</span>
          <span class="skill-tag">React Query</span>
          <span class="skill-tag">React Router v6</span>
          <span class="skill-tag">Context API</span>
          <span class="skill-tag">Vite</span>
        </div>
      </div>
      <div class="skill-group fade-up">
        <div class="skill-group-title">Backend</div>
        <div class="skill-tags">
          <span class="skill-tag">Node.js</span>
          <span class="skill-tag">Express.js</span>
          <span class="skill-tag">REST API</span>
          <span class="skill-tag">JWT Auth</span>
          <span class="skill-tag">bcrypt</span>
          <span class="skill-tag">MVC Architecture</span>
          <span class="skill-tag">Rate Limiting</span>
          <span class="skill-tag">Nodemailer</span>
        </div>
      </div>
      <div class="skill-group fade-up">
        <div class="skill-group-title">Database & Cloud</div>
        <div class="skill-tags">
          <span class="skill-tag">MongoDB</span>
          <span class="skill-tag">Mongoose ODM</span>
          <span class="skill-tag">MySQL</span>
          <span class="skill-tag">MongoDB Atlas</span>
          <span class="skill-tag">Vercel</span>
          <span class="skill-tag">Render</span>
        </div>
      </div>
      <div class="skill-group fade-up">
        <div class="skill-group-title">Languages & Tools</div>
        <div class="skill-tags">
          <span class="skill-tag">Python</span>
          <span class="skill-tag">Java</span>
          <span class="skill-tag">C</span>
          <span class="skill-tag">MicroPython</span>
          <span class="skill-tag">Git</span>
          <span class="skill-tag">GitHub</span>
          <span class="skill-tag">Postman</span>
          <span class="skill-tag">VS Code</span>
          <span class="skill-tag">Power BI</span>
        </div>
      </div>
    </div>
  </div>
</section>

<section id="projects">
  <div class="container">
    <div class="fade-up">
      <span class="section-label">// work</span>
      <h2 class="section-title">Projects</h2>
      <div class="section-line"></div>
    </div>
    <div class="projects-grid">
      <div class="project-card fade-up">
        <div class="project-icon">✅</div>
        <div class="project-title">TaskFlow — Task & Project Manager</div>
        <div class="project-desc">Full stack Kanban project manager with JWT authentication, protected React routes, and real-time task status updates. MVC REST API on Node.js/Express with Mongoose ODM.</div>
        <div class="project-metrics">
          <span class="metric">60% fewer API calls</span>
          <span class="metric">Deployed on Vercel + Render</span>
        </div>
        <div class="project-tech">
          <span class="tech-badge">React.js</span>
          <span class="tech-badge">Node.js</span>
          <span class="tech-badge">MongoDB</span>
          <span class="tech-badge">JWT</span>
          <span class="tech-badge">React Query</span>
          <span class="tech-badge">bcrypt</span>
        </div>
        <div class="project-links">
          <a href="https://github.com/Shre477/taskflow" target="_blank" class="project-link">GitHub →</a>
        </div>
      </div>
      <div class="project-card fade-up">
        <div class="project-icon">🛒</div>
        <div class="project-title">E-Commerce Website</div>
        <div class="project-desc">Full stack e-commerce platform with product listing, cart management, and user authentication. Led entire frontend architecture as frontend lead in a 4-member team.</div>
        <div class="project-metrics">
          <span class="metric">Frontend Lead</span>
          <span class="metric">4-member team</span>
        </div>
        <div class="project-tech">
          <span class="tech-badge">React.js</span>
          <span class="tech-badge">Node.js</span>
          <span class="tech-badge">MongoDB</span>
          <span class="tech-badge">REST API</span>
          <span class="tech-badge">CSS3</span>
        </div>
        <div class="project-links">
          <a href="https://github.com/Shre477/ecommerce-website_Project" target="_blank" class="project-link">GitHub →</a>
        </div>
      </div>
      <div class="project-card fade-up">
        <div class="project-icon">🍽️</div>
        <div class="project-title">Food Ordering Website</div>
        <div class="project-desc">React food menu app with live REST API integration and dynamic cart. Reusable component architecture reduced codebase by 30%. Built with a 3-member team.</div>
        <div class="project-metrics">
          <span class="metric">30% less code</span>
          <span class="metric">Cert: ARDENT/2023/AD98864</span>
        </div>
        <div class="project-tech">
          <span class="tech-badge">React.js</span>
          <span class="tech-badge">REST API</span>
          <span class="tech-badge">HTML5</span>
          <span class="tech-badge">CSS3</span>
        </div>
        <div class="project-links">
          <a href="https://github.com/Shre477/foodmenu-website_project" target="_blank" class="project-link">GitHub →</a>
        </div>
      </div>
      <div class="project-card fade-up">
        <div class="project-icon">💡</div>
        <div class="project-title">Smart Street Light — IoT</div>
        <div class="project-desc">Automated street light using MicroPython with dual-sensor (motion + LDR) auto-switching. Calibrated sensor thresholds for real-world reliability.</div>
        <div class="project-metrics">
          <span class="metric">40% energy reduction</span>
          <span class="metric">Cert: ARDENT/116834</span>
        </div>
        <div class="project-tech">
          <span class="tech-badge">MicroPython</span>
          <span class="tech-badge">IoT Sensors</span>
          <span class="tech-badge">Embedded Systems</span>
        </div>
        <div class="project-links">
          <span class="project-link" style="color:var(--muted);cursor:default">Private Repo</span>
        </div>
      </div>
    </div>
  </div>
</section>

<section id="dsa">
  <div class="container">
    <div class="fade-up">
      <span class="section-label">// problem solving</span>
      <h2 class="section-title">DSA & Algorithms</h2>
      <div class="section-line"></div>
    </div>
    <div class="dsa-content fade-up">
      <div class="dsa-left">
        <p>Actively solving problems on LeetCode to prepare for product-based company interviews. Focus on algorithmic thinking, time & space complexity optimization.</p>
        <div class="dsa-topics">
          <div class="dsa-topic"><span class="topic-name">Arrays & Strings</span><div class="topic-bar-wrap"><div class="topic-bar" data-width="85" style="width:0%"></div></div></div>
          <div class="dsa-topic"><span class="topic-name">HashMap & HashSet</span><div class="topic-bar-wrap"><div class="topic-bar" data-width="80" style="width:0%"></div></div></div>
          <div class="dsa-topic"><span class="topic-name">Sliding Window</span><div class="topic-bar-wrap"><div class="topic-bar" data-width="70" style="width:0%"></div></div></div>
          <div class="dsa-topic"><span class="topic-name">Two Pointers</span><div class="topic-bar-wrap"><div class="topic-bar" data-width="68" style="width:0%"></div></div></div>
          <div class="dsa-topic"><span class="topic-name">Trees & Graphs</span><div class="topic-bar-wrap"><div class="topic-bar" data-width="55" style="width:0%"></div></div></div>
          <div class="dsa-topic"><span class="topic-name">Dynamic Programming</span><div class="topic-bar-wrap"><div class="topic-bar" data-width="45" style="width:0%"></div></div></div>
        </div>
        <a href="https://leetcode.com/u/shreya-patra-7005a1234/" target="_blank" class="dsa-link">View LeetCode Profile →</a>
      </div>
      <div class="dsa-right">
        <div class="dsa-stat"><div class="dsa-stat-num">Active</div><div class="dsa-stat-label">Daily Practice Streak</div></div>
        <div class="dsa-stat"><div class="dsa-stat-num">DSA</div><div class="dsa-stat-label">Focus: Arrays · Trees · DP · Graphs</div></div>
        <div class="dsa-stat"><div class="dsa-stat-num">Java</div><div class="dsa-stat-label">Primary language for DSA</div></div>
        <div class="dsa-stat"><div class="dsa-stat-num">2026</div><div class="dsa-stat-label">Target: Product-Based SWE Role</div></div>
      </div>
    </div>
  </div>
</section>

<section id="education">
  <div class="container">
    <div class="fade-up">
      <span class="section-label">// background</span>
      <h2 class="section-title">Education</h2>
      <div class="section-line"></div>
    </div>
    <div class="edu-timeline fade-up">
      <div class="edu-item">
        <div class="edu-year">2022 — 2026</div>
        <div class="edu-degree">B.Tech in Computer Science Engineering</div>
        <div class="edu-school">Dr. Sudhir Chandra Sur Institute of Technology, Kolkata</div>
        <div style="margin-top:.5rem;color:var(--muted);font-size:.85rem">DSA · DBMS · OOP · OS · Computer Networks · Software Engineering · IoT</div>
      </div>
      <div class="edu-item">
        <div class="edu-year">2022</div>
        <div class="edu-degree">Class XII — WBCHSE</div>
        <div class="edu-school">Goura Sonamui K.B.A Sikshayatan</div>
        <span class="edu-score">92%</span>
      </div>
      <div class="edu-item">
        <div class="edu-year">2020</div>
        <div class="edu-degree">Class X — WBSC</div>
        <div class="edu-school">Goura Sonamui K.B.A Sikshayatan</div>
        <span class="edu-score">88%</span>
      </div>
    </div>
    <div style="margin-top:3rem" class="fade-up">
      <span class="section-label">// certifications</span>
      <div style="display:flex;gap:1rem;flex-wrap:wrap;margin-top:1rem">
        <div style="background:var(--card);border:1px solid var(--border);border-radius:10px;padding:1rem 1.5rem">
          <div style="color:var(--accent);font-size:.75rem;font-family:'JetBrains Mono',monospace;margin-bottom:.3rem">ARDENT/2023/AD98864</div>
          <div style="font-size:.9rem;font-weight:500">Web Development</div>
          <div style="color:var(--muted);font-size:.8rem">Ardent Software</div>
        </div>
        <div style="background:var(--card);border:1px solid var(--border);border-radius:10px;padding:1rem 1.5rem">
          <div style="color:var(--accent);font-size:.75rem;font-family:'JetBrains Mono',monospace;margin-bottom:.3rem">ARDENT/116834</div>
          <div style="font-size:.9rem;font-weight:500">IoT Systems</div>
          <div style="color:var(--muted);font-size:.8rem">Ardent Software</div>
        </div>
      </div>
    </div>
  </div>
</section>

<section id="contact">
  <div class="container">
    <div class="contact-inner fade-up">
      <span class="section-label">// let's connect</span>
      <h2 class="section-title">Open to Opportunities</h2>
      <div class="section-line" style="margin:1rem auto 2rem"></div>
      <p>Seeking Full Stack Developer / SWE roles at product-based companies. Available from May 2026. Let's build something great together.</p>
      <div class="contact-links">
        <a href="https://www.linkedin.com/in/shreya-p-737526301" target="_blank" class="contact-link">LinkedIn</a>
        <a href="https://github.com/Shre477" target="_blank" class="contact-link">GitHub</a>
        <a href="https://leetcode.com/u/shreya-patra-7005a1234/" target="_blank" class="contact-link">LeetCode</a>
        <a href="mailto:Patrashreya477@gmail.com" class="contact-link">Email Me</a>
      </div>
      <div class="contact-email">Patrashreya477@gmail.com · +91 8372053836</div>
    </div>
  </div>
</section>

<footer>
  Built by <span>Shreya Patra</span> · Full Stack Developer · Kolkata, India
</footer>

<script>
const cursor=document.getElementById('cursor');
const ring=document.getElementById('cursorRing');
let mx=0,my=0,rx=0,ry=0;
document.addEventListener('mousemove',e=>{mx=e.clientX;my=e.clientY;cursor.style.left=mx-5+'px';cursor.style.top=my-5+'px'});
function animRing(){rx+=(mx-rx)*.12;ry+=(my-ry)*.12;ring.style.left=rx-18+'px';ring.style.top=ry-18+'px';requestAnimationFrame(animRing)}
animRing();
document.querySelectorAll('a,button').forEach(el=>{
  el.addEventListener('mouseenter',()=>{cursor.style.transform='scale(2)';ring.style.transform='scale(1.5)'});
  el.addEventListener('mouseleave',()=>{cursor.style.transform='scale(1)';ring.style.transform='scale(1)'});
});

const observer=new IntersectionObserver(entries=>{
  entries.forEach(e=>{if(e.isIntersecting){e.target.classList.add('visible')}});
},{threshold:.15});
document.querySelectorAll('.fade-up').forEach(el=>observer.observe(el));

const barObserver=new IntersectionObserver(entries=>{
  entries.forEach(e=>{
    if(e.isIntersecting){
      e.target.querySelectorAll('.topic-bar').forEach(bar=>{
        bar.style.width=bar.dataset.width+'%';
      });
    }
  });
},{threshold:.3});
document.querySelectorAll('#dsa').forEach(el=>barObserver.observe(el));

document.querySelectorAll('a[href^="#"]').forEach(a=>{
  a.addEventListener('click',e=>{
    e.preventDefault();
    document.querySelector(a.getAttribute('href')).scrollIntoView({behavior:'smooth'});
  });
});
</script>
</body>
</html>
