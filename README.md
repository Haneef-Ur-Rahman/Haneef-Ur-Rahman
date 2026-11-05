<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<meta name="description" content="Haneef Ur Rahman — Front-End Engineer & MERN Stack Developer. Building responsive, user-focused web applications." />
<title>Haneef Ur Rahman — Front-End Engineer</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800;900&family=Space+Grotesk:wght@500;600;700&display=swap" rel="stylesheet">
<style>
  *{margin:0;padding:0;box-sizing:border-box}
  :root{
    --bg:#0a0a0f;
    --bg-2:#0f0f18;
    --card:#12121c;
    --card-2:#1a1a28;
    --border:rgba(255,255,255,0.08);
    --text:#e8e8f0;
    --muted:#8b8ba7;
    --accent:#6c5ce7;
    --accent-2:#00d4ff;
    --accent-3:#ff6b9d;
    --gradient:linear-gradient(135deg,#6c5ce7 0%,#00d4ff 100%);
    --gradient-2:linear-gradient(135deg,#ff6b9d 0%,#6c5ce7 100%);
  }
  html{scroll-behavior:smooth}
  body{
    font-family:'Inter',sans-serif;
    background:var(--bg);
    color:var(--text);
    line-height:1.6;
    overflow-x:hidden;
    -webkit-font-smoothing:antialiased;
  }
  a{color:inherit;text-decoration:none}
  img{max-width:100%;display:block}
  ::selection{background:var(--accent);color:#fff}

  /* Background glow */
  .bg-glow{
    position:fixed;inset:0;z-index:-1;overflow:hidden;pointer-events:none;
  }
  .bg-glow::before,
  .bg-glow::after{
    content:'';position:absolute;border-radius:50%;filter:blur(120px);opacity:.35;
  }
  .bg-glow::before{
    width:500px;height:500px;background:#6c5ce7;
    top:-150px;left:-150px;
    animation:float1 18s ease-in-out infinite;
  }
  .bg-glow::after{
    width:600px;height:600px;background:#00d4ff;
    bottom:-200px;right:-200px;
    animation:float2 22s ease-in-out infinite;
  }
  @keyframes float1{50%{transform:translate(80px,60px) scale(1.15)}}
  @keyframes float2{50%{transform:translate(-80px,-60px) scale(1.1)}}

  /* Nav */
  nav{
    position:fixed;top:0;left:0;right:0;z-index:100;
    padding:16px 0;
    backdrop-filter:blur(16px);
    -webkit-backdrop-filter:blur(16px);
    background:rgba(10,10,15,0.7);
    border-bottom:1px solid var(--border);
    transition:all .3s ease;
  }
  .nav-inner{
    max-width:1200px;margin:0 auto;padding:0 32px;
    display:flex;justify-content:space-between;align-items:center;
  }
  .logo{
    font-family:'Space Grotesk',sans-serif;
    font-weight:700;font-size:1.25rem;
    background:var(--gradient);
    -webkit-background-clip:text;background-clip:text;
    -webkit-text-fill-color:transparent;
    letter-spacing:-.02em;
  }
  .nav-links{display:flex;gap:32px;list-style:none}
  .nav-links a{
    font-size:.9rem;font-weight:500;color:var(--muted);
    position:relative;transition:color .25s ease;
  }
  .nav-links a::after{
    content:'';position:absolute;bottom:-4px;left:0;
    width:0;height:2px;background:var(--gradient);
    transition:width .3s ease;
  }
  .nav-links a:hover{color:var(--text)}
  .nav-links a:hover::after{width:100%}
  .menu-btn{display:none;background:none;border:none;color:var(--text);font-size:1.5rem;cursor:pointer}

  /* Hero */
  .hero{
    min-height:100vh;
    display:flex;align-items:center;
    padding:120px 32px 80px;
    position:relative;
  }
  .hero-inner{
    max-width:1200px;margin:0 auto;width:100%;
    display:grid;grid-template-columns:1.2fr 1fr;gap:80px;align-items:center;
  }
  .hero-badge{
    display:inline-flex;align-items:center;gap:8px;
    padding:6px 16px;border-radius:100px;
    background:rgba(108,92,231,0.1);
    border:1px solid rgba(108,92,231,0.3);
    font-size:.85rem;color:#a29bfe;font-weight:500;
    margin-bottom:24px;
  }
  .hero-badge .dot{
    width:8px;height:8px;border-radius:50%;background:#00ff88;
    box-shadow:0 0 12px #00ff88;
    animation:pulse 2s ease-in-out infinite;
  }
  @keyframes pulse{50%{opacity:.5}}
  .hero h1{
    font-family:'Space Grotesk',sans-serif;
    font-size:clamp(2.5rem,5.5vw,4.5rem);
    line-height:1.05;font-weight:700;
    letter-spacing:-.03em;margin-bottom:24px;
  }
  .hero h1 .gradient{
    background:var(--gradient);
    -webkit-background-clip:text;background-clip:text;
    -webkit-text-fill-color:transparent;
  }
  .hero p.lead{
    font-size:1.15rem;color:var(--muted);
    max-width:540px;margin-bottom:36px;line-height:1.7;
  }
  .hero-actions{display:flex;gap:16px;flex-wrap:wrap;margin-bottom:48px}
  .btn{
    display:inline-flex;align-items:center;gap:10px;
    padding:14px 28px;border-radius:12px;
    font-weight:600;font-size:.95rem;cursor:pointer;
    transition:all .3s ease;border:none;
    font-family:'Inter',sans-serif;
  }
  .btn-primary{
    background:var(--gradient);color:#fff;
    box-shadow:0 8px 30px rgba(108,92,231,0.35);
  }
  .btn-primary:hover{transform:translateY(-2px);box-shadow:0 12px 40px rgba(108,92,231,0.5)}
  .btn-ghost{
    background:rgba(255,255,255,0.04);
    color:var(--text);border:1px solid var(--border);
  }
  .btn-ghost:hover{background:rgba(255,255,255,0.08);border-color:rgba(255,255,255,0.2)}

  .hero-stats{display:flex;gap:40px;flex-wrap:wrap}
  .stat .num{
    font-family:'Space Grotesk',sans-serif;
    font-size:2rem;font-weight:700;
    background:var(--gradient);
    -webkit-background-clip:text;background-clip:text;
    -webkit-text-fill-color:transparent;
  }
  .stat .label{font-size:.85rem;color:var(--muted);margin-top:4px}

  /* Hero card (banner) */
  .hero-visual{position:relative}
  .hero-visual::before{
    content:'';position:absolute;inset:-20px;
    background:var(--gradient);border-radius:24px;
    filter:blur(40px);opacity:.4;z-index:-1;
  }
  .hero-visual img{
    border-radius:20px;border:1px solid var(--border);
    box-shadow:0 30px 80px rgba(0,0,0,0.6);
    transition:transform .5s ease;
  }
  .hero-visual img:hover{transform:translateY(-6px) scale(1.02)}

  /* Section */
  section{padding:100px 32px;position:relative}
  .container{max-width:1200px;margin:0 auto}
  .section-head{margin-bottom:64px;text-align:center}
  .section-tag{
    display:inline-block;
    font-size:.8rem;font-weight:600;letter-spacing:.15em;
    text-transform:uppercase;color:var(--accent-2);
    margin-bottom:16px;
  }
  .section-title{
    font-family:'Space Grotesk',sans-serif;
    font-size:clamp(2rem,4vw,3rem);
    font-weight:700;letter-spacing:-.02em;line-height:1.15;
    margin-bottom:16px;
  }
  .section-sub{
    color:var(--muted);font-size:1.05rem;
    max-width:600px;margin:0 auto;
  }

  /* About */
  .about-grid{display:grid;grid-template-columns:1fr 1.3fr;gap:64px;align-items:center}
  .about-card{
    background:var(--card);
    border:1px solid var(--border);border-radius:20px;
    padding:40px;position:relative;overflow:hidden;
  }
  .about-card::before{
    content:'';position:absolute;top:0;left:0;right:0;height:2px;
    background:var(--gradient);
  }
  .about-card h3{
    font-family:'Space Grotesk',sans-serif;
    font-size:1.5rem;margin-bottom:16px;
  }
  .about-card p{color:var(--muted);margin-bottom:16px;line-height:1.75}
  .about-list{list-style:none;margin-top:24px}
  .about-list li{
    display:flex;align-items:flex-start;gap:12px;
    padding:10px 0;color:var(--text);font-size:.95rem;
  }
  .about-list li::before{
    content:'→';color:var(--accent-2);font-weight:700;flex-shrink:0;
  }

  /* Skills */
  .skills-grid{
    display:grid;
    grid-template-columns:repeat(auto-fit,minmax(240px,1fr));
    gap:24px;
  }
  .skill-card{
    background:var(--card);
    border:1px solid var(--border);border-radius:16px;
    padding:28px;transition:all .35s ease;
    position:relative;overflow:hidden;
  }
  .skill-card::before{
    content:'';position:absolute;inset:0;
    background:var(--gradient);opacity:0;
    transition:opacity .35s ease;
  }
  .skill-card:hover{
    transform:translateY(-4px);
    border-color:rgba(108,92,231,0.4);
    box-shadow:0 20px 40px rgba(108,92,231,0.15);
  }
  .skill-card:hover::before{opacity:.04}
  .skill-icon{
    width:52px;height:52px;border-radius:12px;
    background:rgba(108,92,231,0.12);
    display:flex;align-items:center;justify-content:center;
    font-size:1.6rem;margin-bottom:18px;
    position:relative;z-index:1;
  }
  .skill-card h4{
    font-family:'Space Grotesk',sans-serif;
    font-size:1.1rem;margin-bottom:10px;position:relative;z-index:1;
  }
  .skill-tags{
    display:flex;flex-wrap:wrap;gap:6px;position:relative;z-index:1;
  }
  .skill-tags span{
    font-size:.78rem;padding:4px 10px;border-radius:100px;
    background:rgba(255,255,255,0.05);
    border:1px solid var(--border);
    color:var(--muted);font-weight:500;
  }

  /* Projects */
  .projects-grid{
    display:grid;
    grid-template-columns:repeat(auto-fit,minmax(340px,1fr));
    gap:32px;
  }
  .project-card{
    background:var(--card);
    border:1px solid var(--border);border-radius:20px;
    overflow:hidden;position:relative;
    transition:all .4s ease;
    display:flex;flex-direction:column;
  }
  .project-card:hover{
    transform:translateY(-8px);
    border-color:rgba(108,92,231,0.5);
    box-shadow:0 30px 60px rgba(0,0,0,0.4),0 0 0 1px rgba(108,92,231,0.2);
  }
  .project-cover{
    height:200px;
    background:linear-gradient(135deg,#1a1a28 0%,#12121c 100%);
    display:flex;align-items:center;justify-content:center;
    position:relative;overflow:hidden;
    border-bottom:1px solid var(--border);
  }
  .project-cover::before{
    content:'';position:absolute;inset:0;
    background:radial-gradient(circle at 30% 40%,rgba(108,92,231,0.3),transparent 60%),
               radial-gradient(circle at 70% 60%,rgba(0,212,255,0.25),transparent 60%);
    opacity:.6;
  }
  .project-cover .emoji{
    font-size:4rem;position:relative;z-index:1;
    filter:drop-shadow(0 10px 30px rgba(108,92,231,0.5));
    transition:transform .4s ease;
  }
  .project-card:hover .project-cover .emoji{transform:scale(1.15) rotate(-5deg)}
  .project-badge{
    position:absolute;top:16px;left:16px;
    padding:5px 12px;border-radius:100px;
    font-size:.72rem;font-weight:600;
    background:rgba(0,0,0,0.6);
    backdrop-filter:blur(8px);
    border:1px solid rgba(255,255,255,0.15);
    z-index:2;
  }
  .project-badge.featured{background:rgba(255,107,157,0.2);border-color:rgba(255,107,157,0.4);color:#ffb3cc}
  .project-badge.new{background:rgba(0,255,136,0.15);border-color:rgba(0,255,136,0.4);color:#7dffb8}
  .project-body{padding:28px;flex:1;display:flex;flex-direction:column}
  .project-body h3{
    font-family:'Space Grotesk',sans-serif;
    font-size:1.3rem;margin-bottom:10px;
  }
  .project-body p{
    color:var(--muted);font-size:.92rem;
    margin-bottom:20px;flex:1;line-height:1.7;
  }
  .project-tags{display:flex;flex-wrap:wrap;gap:6px;margin-bottom:20px}
  .project-tags span{
    font-size:.72rem;padding:4px 10px;border-radius:100px;
    background:rgba(108,92,231,0.1);
    border:1px solid rgba(108,92,231,0.25);
    color:#a29bfe;font-weight:500;
  }
  .project-links{display:flex;gap:14px;flex-wrap:wrap}
  .project-links a{
    display:inline-flex;align-items:center;gap:6px;
    font-size:.85rem;font-weight:600;
    color:var(--text);padding:8px 14px;
    border-radius:10px;
    background:rgba(255,255,255,0.05);
    border:1px solid var(--border);
    transition:all .25s ease;
  }
  .project-links a:hover{
    background:rgba(108,92,231,0.15);
    border-color:rgba(108,92,231,0.4);
    color:#a29bfe;
  }
  .project-links a.primary{
    background:var(--gradient);color:#fff;border:none;
  }
  .project-links a.primary:hover{
    box-shadow:0 8px 24px rgba(108,92,231,0.4);
    transform:translateY(-1px);
    color:#fff;
  }

  /* Experience timeline */
  .timeline{position:relative;padding-left:36px}
  .timeline::before{
    content:'';position:absolute;left:8px;top:8px;bottom:8px;
    width:2px;background:var(--gradient);border-radius:2px;
  }
  .timeline-item{
    position:relative;padding-bottom:36px;
  }
  .timeline-item:last-child{padding-bottom:0}
  .timeline-item::before{
    content:'';position:absolute;left:-32px;top:6px;
    width:16px;height:16px;border-radius:50%;
    background:var(--bg);
    border:3px solid var(--accent);
    box-shadow:0 0 0 4px rgba(108,92,231,0.15);
  }
  .timeline-item h4{
    font-family:'Space Grotesk',sans-serif;
    font-size:1.1rem;margin-bottom:4px;
  }
  .timeline-item .meta{
    font-size:.85rem;color:var(--accent-2);
    font-weight:500;margin-bottom:8px;
  }
  .timeline-item p{color:var(--muted);font-size:.92rem;line-height:1.7}

  /* Contact */
  .contact-wrap{
    background:linear-gradient(135deg,rgba(108,92,231,0.08) 0%,rgba(0,212,255,0.05) 100%);
    border:1px solid var(--border);border-radius:24px;
    padding:64px 48px;text-align:center;
    position:relative;overflow:hidden;
  }
  .contact-wrap::before{
    content:'';position:absolute;inset:0;
    background:radial-gradient(circle at 50% 0%,rgba(108,92,231,0.2),transparent 60%);
    pointer-events:none;
  }
  .contact-wrap h2{
    font-family:'Space Grotesk',sans-serif;
    font-size:clamp(1.8rem,4vw,2.75rem);
    margin-bottom:16px;position:relative;
  }
  .contact-wrap p{
    color:var(--muted);max-width:560px;margin:0 auto 36px;
    position:relative;
  }
  .contact-actions{
    display:flex;gap:16px;justify-content:center;flex-wrap:wrap;
    position:relative;
  }

  /* Footer */
  footer{
    padding:48px 32px 32px;
    border-top:1px solid var(--border);
    text-align:center;
  }
  .footer-social{
    display:flex;justify-content:center;gap:16px;
    margin-bottom:24px;flex-wrap:wrap;
  }
  .footer-social a{
    width:44px;height:44px;border-radius:12px;
    background:rgba(255,255,255,0.04);
    border:1px solid var(--border);
    display:flex;align-items:center;justify-content:center;
    transition:all .25s ease;
  }
  .footer-social a:hover{
    background:rgba(108,92,231,0.15);
    border-color:rgba(108,92,231,0.4);
    transform:translateY(-3px);
  }
  .footer-social svg{width:20px;height:20px;fill:var(--muted);transition:fill .25s ease}
  .footer-social a:hover svg{fill:#a29bfe}
  .footer-text{color:var(--muted);font-size:.88rem}
  .footer-text .name{
    background:var(--gradient);
    -webkit-background-clip:text;background-clip:text;
    -webkit-text-fill-color:transparent;font-weight:600;
  }

  /* Reveal on scroll */
  .reveal{opacity:0;transform:translateY(30px);transition:all .7s cubic-bezier(.16,1,.3,1)}
  .reveal.visible{opacity:1;transform:translateY(0)}

  /* Responsive */
  @media(max-width:900px){
    .hero-inner{grid-template-columns:1fr;gap:60px;text-align:center}
    .hero p.lead{margin-left:auto;margin-right:auto}
    .hero-actions,.hero-stats{justify-content:center}
    .hero-visual{max-width:600px;margin:0 auto;order:-1}
    .about-grid{grid-template-columns:1fr;gap:40px}
    .nav-links{display:none}
    .menu-btn{display:block}
    .nav-links.open{
      display:flex;flex-direction:column;
      position:absolute;top:100%;left:0;right:0;
      background:var(--bg-2);
      padding:24px 32px;gap:20px;
      border-bottom:1px solid var(--border);
    }
  }
  @media(max-width:600px){
    section{padding:70px 20px}
    .hero{padding:100px 20px 60px}
    .nav-inner{padding:0 20px}
    .contact-wrap{padding:48px 24px}
    .hero-stats{gap:24px}
    .projects-grid{grid-template-columns:1fr}
  }
</style>
</head>
<body>

<div class="bg-glow"></div>

<nav id="nav">
  <div class="nav-inner">
    <a href="#hero" class="logo">Haneef.dev</a>
    <ul class="nav-links" id="navLinks">
      <li><a href="#about">About</a></li>
      <li><a href="#skills">Skills</a></li>
      <li><a href="#projects">Projects</a></li>
      <li><a href="#experience">Experience</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
    <button class="menu-btn" id="menuBtn" aria-label="Menu">☰</button>
  </div>
</nav>

<!-- HERO -->
<section class="hero" id="hero">
  <div class="hero-inner">
    <div>
      <div class="hero-badge"><span class="dot"></span> Available for freelance & collaborations</div>
      <h1>Building <span class="gradient">digital experiences</span> that users love.</h1>
      <p class="lead">
        I'm <strong>Haneef Ur Rahman</strong> — a Front-End Engineer & MERN Stack Developer from Peshawar, Pakistan.
        I craft responsive, accessible and fast web applications with React, TypeScript, Tailwind and Node.js.
      </p>
      <div class="hero-actions">
        <a href="#projects" class="btn btn-primary">View My Work →</a>
        <a href="mailto:haneef04022004@gmail.com" class="btn btn-ghost">Hire Me</a>
      </div>
      <div class="hero-stats">
        <div class="stat"><div class="num">10+</div><div class="label">Projects</div></div>
        <div class="stat"><div class="num">3.66</div><div class="label">CGPA</div></div>
        <div class="stat"><div class="num">2026</div><div class="label">Graduating</div></div>
      </div>
    </div>
    <div class="hero-visual">
      <img src="https://raw.githubusercontent.com/Haneef-Ur-Rahman/Haneef-Ur-Rahman/main/assets/LinkedIn%20Banner4.png" alt="Haneef Ur Rahman" />
    </div>
  </div>
</section>

<!-- ABOUT -->
<section id="about">
  <div class="container">
    <div class="section-head reveal">
      <div class="section-tag">About Me</div>
      <h2 class="section-title">Turning ideas into<br/>clean, working products.</h2>
    </div>
    <div class="about-grid">
      <div class="about-card reveal">
        <h3>👋 A bit about me</h3>
        <p>
          I'm a CS undergraduate at the University of Peshawar with a passion for frontend
          engineering and full-stack development. I love building tools that solve real problems —
          from campus library systems to welfare society platforms.
        </p>
        <p>
          My approach: <strong>clean code, thoughtful design, seamless UX</strong>. I care about
          accessibility, performance and the small details that make interfaces feel right.
        </p>
      </div>
      <div class="reveal">
        <ul class="about-list">
          <li><strong>Currently building</strong> BiblioTrack — a Smart Library Management System (Final Year Project)</li>
          <li><strong>Exploring</strong> Cloud Computing, AWS Fundamentals & Applied ML (NLP)</li>
          <li><strong>Worked as</strong> Web Developer at Digital Empowerment Network (Jul–Sep 2025)</li>
          <li><strong>Open to</strong> freelance work, internships & open-source collaborations</li>
          <li><strong>Leadership</strong> Management Lead @ Wrapify Labs, CSSC Member, CR, Lead Volunteer @ Saylani</li>
          <li><strong>Fun fact</strong> I build tools for my own campus before anyone asks me to</li>
        </ul>
      </div>
    </div>
  </div>
</section>

<!-- SKILLS -->
<section id="skills">
  <div class="container">
    <div class="section-head reveal">
      <div class="section-tag">Tech Stack</div>
      <h2 class="section-title">Tools I use to build.</h2>
      <p class="section-sub">Modern, battle-tested technologies for the frontend, backend and everything in between.</p>
    </div>
    <div class="skills-grid">
      <div class="skill-card reveal">
        <div class="skill-icon">🎨</div>
        <h4>Frontend</h4>
        <div class="skill-tags">
          <span>React.js</span><span>JavaScript</span><span>TypeScript</span>
          <span>Tailwind</span><span>Bootstrap</span><span>HTML5</span><span>CSS3</span>
        </div>
      </div>
      <div class="skill-card reveal">
        <div class="skill-icon">⚙️</div>
        <h4>Backend</h4>
        <div class="skill-tags">
          <span>Node.js</span><span>Express.js</span><span>MongoDB</span>
          <span>MySQL</span><span>REST APIs</span><span>PHP</span>
        </div>
      </div>
      <div class="skill-card reveal">
        <div class="skill-icon">☁️</div>
        <h4>Cloud & Services</h4>
        <div class="skill-tags">
          <span>Firebase</span><span>Firestore</span><span>AWS (Fundamentals)</span>
          <span>Vercel</span>
        </div>
      </div>
      <div class="skill-card reveal">
        <div class="skill-icon">🛠️</div>
        <h4>Tools & Workflow</h4>
        <div class="skill-tags">
          <span>Git</span><span>GitHub</span><span>Figma</span>
          <span>Agile / SCRUM</span><span>Postman</span>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- PROJECTS -->
<section id="projects">
  <div class="container">
    <div class="section-head reveal">
      <div class="section-tag">Featured Work</div>
      <h2 class="section-title">Projects I'm proud of.</h2>
      <p class="section-sub">A selection of things I've designed, coded and shipped. More on <a href="https://github.com/Haneef-Ur-Rahman?tab=repositories" style="color:var(--accent-2);text-decoration:underline">GitHub</a>.</p>
    </div>
    <div class="projects-grid">

      <!-- BiblioTrack -->
      <div class="project-card reveal">
        <div class="project-cover">
          <span class="project-badge featured">⭐ Final Year Project</span>
          <span class="emoji">📚</span>
        </div>
        <div class="project-body">
          <h3>BiblioTrack — Smart Library System</h3>
          <p>
            Full-stack library management platform for the CS Department, University of Peshawar.
            Admin & Student portals, smart reservations, AI chatbot, automated fines & email notifications.
          </p>
          <div class="project-tags">
            <span>React</span><span>Node.js</span><span>Express</span><span>MongoDB</span><span>Tailwind</span>
          </div>
          <div class="project-links">
            <a href="https://bibliotrack-smart-library.vercel.app/" target="_blank" class="primary">Live Demo →</a>
            <a href="https://github.com/Haneef-Ur-Rahman/bibliotrack-smart-library" target="_blank">Code</a>
          </div>
        </div>
      </div>

      <!-- Hassan Welfare -->
      <div class="project-card reveal">
        <div class="project-cover">
          <span class="project-badge new">Live</span>
          <span class="emoji">❤️</span>
        </div>
        <div class="project-body">
          <h3>Hassan Welfare Society Website</h3>
          <p>
            Informative, responsive website showcasing the society's mission, vision, members and
            donation contribution details — built with React and deployed on Firebase.
          </p>
          <div class="project-tags">
            <span>React.js</span><span>Firebase</span><span>HTML5</span><span>CSS3</span>
          </div>
          <div class="project-links">
            <a href="https://fir-database1-debbe.web.app/" target="_blank" class="primary">Live Demo →</a>
            <a href="https://github.com/Haneef-Ur-Rahman/react-welfare-website" target="_blank">Code</a>
          </div>
        </div>
      </div>

      <!-- E-commerce -->
      <div class="project-card reveal">
        <div class="project-cover">
          <span class="project-badge">4th Semester</span>
          <span class="emoji">🛒</span>
        </div>
        <div class="project-body">
          <h3>E-Commerce Platform</h3>
          <p>
            Full-stack e-commerce platform with secure cart and checkout flow. Mobile-first,
            interactive UI powered by React, Node.js and Bootstrap.
          </p>
          <div class="project-tags">
            <span>React</span><span>Node.js</span><span>Bootstrap</span><span>JavaScript</span>
          </div>
          <div class="project-links">
            <a href="https://github.com/Haneef-Ur-Rahman?tab=repositories" target="_blank" class="primary">View Repo →</a>
          </div>
        </div>
      </div>

      <!-- Backend Projects -->
      <div class="project-card reveal">
        <div class="project-cover">
          <span class="project-badge">Backend</span>
          <span class="emoji">🗄️</span>
        </div>
        <div class="project-body">
          <h3>BackEnd Projects</h3>
          <p>
            Collection of server-side services and RESTful APIs built with Node.js, Express and MongoDB —
            covering routing, middleware, authentication and CRUD operations.
          </p>
          <div class="project-tags">
            <span>Node.js</span><span>Express.js</span><span>MongoDB</span><span>REST APIs</span>
          </div>
          <div class="project-links">
            <a href="https://github.com/Haneef-Ur-Rahman/backEnd" target="_blank" class="primary">View Repo →</a>
          </div>
        </div>
      </div>

      <!-- Portfolio -->
      <div class="project-card reveal">
        <div class="project-cover">
          <span class="project-badge new">Live</span>
          <span class="emoji">🌐</span>
        </div>
        <div class="project-body">
          <h3>Personal Portfolio</h3>
          <p>
            My personal portfolio website — clean, fast and fully responsive. Built from scratch
            to showcase projects, skills and experience.
          </p>
          <div class="project-tags">
            <span>HTML5</span><span>CSS3</span><span>JavaScript</span>
          </div>
          <div class="project-links">
            <a href="https://haneef-ur-rahman.github.io/my-Portfolio" target="_blank" class="primary">Live Site →</a>
            <a href="https://github.com/Haneef-Ur-Rahman?tab=repositories" target="_blank">All Repos</a>
          </div>
        </div>
      </div>

      <!-- Practice repos -->
      <div class="project-card reveal">
        <div class="project-cover">
          <span class="project-badge">Learning</span>
          <span class="emoji">🧪</span>
        </div>
        <div class="project-body">
          <h3>Practice & Learning Repos</h3>
          <p>
            TypeScript, JavaScript and component-building exercises — including build-practice,
            CodeAlpha tasks, CountryInfoHub and other experiments documenting my journey.
          </p>
          <div class="project-tags">
            <span>TypeScript</span><span>JavaScript</span><span>HTML</span><span>CSS</span>
          </div>
          <div class="project-links">
            <a href="https://github.com/Haneef-Ur-Rahman?tab=repositories" target="_blank" class="primary">Browse All →</a>
          </div>
        </div>
      </div>

    </div>
  </div>
</section>

<!-- EXPERIENCE -->
<section id="experience">
  <div class="container">
    <div class="section-head reveal">
      <div class="section-tag">Journey</div>
      <h2 class="section-title">Experience & milestones.</h2>
    </div>
    <div class="timeline reveal">
      <div class="timeline-item">
        <h4>Web Developer — Digital Empowerment Network</h4>
        <div class="meta">Jul 2025 – Sep 2025</div>
        <p>Built responsive, accessible frontend interfaces with React.js & Tailwind CSS. Developed backend services with Node.js, Express.js & MongoDB, exposed RESTful APIs, and integrated Firebase for secure auth and real-time data.</p>
      </div>
      <div class="timeline-item">
        <h4>Modern Web & Mobile App Development — SMIT Peshawar</h4>
        <div class="meta">Sep 2024 – Mar 2026 (Expected)</div>
        <p>Hands-on training in MongoDB, Express.js, React.js and Node.js for full-stack development.</p>
      </div>
      <div class="timeline-item">
        <h4>BS Computer Science — University of Peshawar</h4>
        <div class="meta">2022 – 2026 · CGPA 3.66 / 4.00</div>
        <p>Focused on web technologies, software engineering, databases and applied ML. Recipient of PMYLS Laptop Scheme 2025 on academic excellence.</p>
      </div>
      <div class="timeline-item">
        <h4>Management Lead — Wrapify Labs, UOP Chapter</h4>
        <div class="meta">Feb 2026 – Present</div>
        <p>Lead team activities for university chapter events, workshops and competitions. Also active in CSSC, as Class Representative and Lead Volunteer at Saylani Welfare.</p>
      </div>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <div class="container">
    <div class="contact-wrap reveal">
      <h2>Let's build something <span style="background:var(--gradient);-webkit-background-clip:text;background-clip:text;-webkit-text-fill-color:transparent">great together.</span></h2>
      <p>Have a project, a role, or just want to say hi? I'm always open to interesting conversations and new opportunities.</p>
      <div class="contact-actions">
        <a href="mailto:haneef04022004@gmail.com" class="btn btn-primary">📩 Email Me</a>
        <a href="https://wa.me/923083336559" class="btn btn-ghost">💬 WhatsApp</a>
        <a href="https://www.linkedin.com/in/haneef-ur-rahman/" class="btn btn-ghost">🔗 LinkedIn</a>
      </div>
    </div>
  </div>
</section>

<footer>
  <div class="footer-social">
    <a href="https://github.com/Haneef-Ur-Rahman" target="_blank" aria-label="GitHub">
      <svg viewBox="0 0 24 24"><path d="M12 .5C5.7.5.5 5.7.5 12c0 5.1 3.3 9.4 7.9 10.9.6.1.8-.3.8-.6v-2c-3.2.7-3.9-1.5-3.9-1.5-.5-1.3-1.3-1.7-1.3-1.7-1.1-.7.1-.7.1-.7 1.2.1 1.8 1.2 1.8 1.2 1 1.8 2.7 1.3 3.4 1 .1-.8.4-1.3.8-1.6-2.6-.3-5.3-1.3-5.3-5.8 0-1.3.5-2.3 1.2-3.1-.1-.3-.5-1.5.1-3.1 0 0 1-.3 3.3 1.2a11.5 11.5 0 0 1 6 0c2.3-1.5 3.3-1.2 3.3-1.2.6 1.6.2 2.8.1 3.1.8.8 1.2 1.8 1.2 3.1 0 4.5-2.7 5.5-5.3 5.8.4.4.8 1.1.8 2.2v3.3c0 .3.2.7.8.6 4.6-1.5 7.9-5.8 7.9-10.9C23.5 5.7 18.3.5 12 .5z"/></svg>
    </a>
    <a href="https://www.linkedin.com/in/haneef-ur-rahman/" target="_blank" aria-label="LinkedIn">
      <svg viewBox="0 0 24 24"><path d="M20.4 20.4h-3.5v-5.6c0-1.3 0-3-1.9-3s-2.1 1.4-2.1 2.9v5.7H9.4V9h3.3v1.6h.1c.5-.9 1.6-1.9 3.4-1.9 3.6 0 4.3 2.4 4.3 5.5v6.2zM5.3 7.4a2 2 0 1 1 0-4.1 2 2 0 0 1 0 4.1zM7.1 20.4H3.6V9h3.5v11.4zM22.2 0H1.8C.8 0 0 .8 0 1.7v20.5C0 23.2.8 24 1.8 24h20.4c1 0 1.8-.8 1.8-1.8V1.7C24 .8 23.2 0 22.2 0z"/></svg>
    </a>
    <a href="mailto:haneef04022004@gmail.com" aria-label="Email">
      <svg viewBox="0 0 24 24"><path d="M20 4H4a2 2 0 0 0-2 2v12a2 2 0 0 0 2 2h16a2 2 0 0 0 2-2V6a2 2 0 0 0-2-2zm0 4-8 5-8-5V6l8 5 8-5v2z"/></svg>
    </a>
    <a href="https://wa.me/923083336559" aria-label="WhatsApp">
      <svg viewBox="0 0 24 24"><path d="M.06 24l1.7-6.2A11.9 11.9 0 0 1 .15 11.9C.15 5.4 5.4.15 11.9.15S23.65 5.4 23.65 11.9s-5.25 11.75-11.75 11.75a11.7 11.7 0 0 1-5.6-1.4L.06 24zm6.6-3.6c1.6.9 3.3 1.4 5.2 1.4 5.4 0 9.8-4.4 9.8-9.9S17.3 2.1 11.9 2.1 2.1 6.5 2.1 11.9c0 1.9.5 3.7 1.5 5.2l-1 3.6 3.6-.9 1.5.8zM17 14.6c-.1-.2-.4-.3-.9-.5-.4-.2-2.5-1.2-2.9-1.4-.4-.1-.7-.2-1 .2-.3.4-1.1 1.4-1.4 1.7-.3.3-.5.3-.9.1-.4-.2-1.8-.7-3.4-2.1-1.3-1.1-2.1-2.5-2.4-2.9-.2-.4 0-.6.2-.8.2-.2.4-.5.6-.7.2-.2.2-.4.3-.6.1-.2 0-.5 0-.7-.1-.2-1-2.4-1.3-3.3-.3-.9-.7-.8-1-.8h-.8c-.3 0-.7.1-1 .5-.3.4-1.3 1.3-1.3 3.1 0 1.9 1.4 3.6 1.6 3.9.2.3 2.7 4.1 6.6 5.8.9.4 1.6.6 2.2.8.9.3 1.7.3 2.4.2.7-.1 2.5-1 2.9-2 .3-1 .3-1.8.2-2z"/></svg>
    </a>
    <a href="https://linktr.ee/Haneef_Ur_Rahman" aria-label="Linktree">
      <svg viewBox="0 0 24 24"><path d="M7.9 20.2h8.2v-3.5H7.9v3.5zM2 10.3l3.1 2.4L1 16.3l2.3 1.6 4.2-4.6v9.4h3.4v-9.4l4.3 4.7 2.2-1.7-4-3.7 3-2.4-2-2-3.5 3.5V3h-3.4v8.7L4.1 8.3 2 10.3z"/></svg>
    </a>
  </div>
  <p class="footer-text">© <span id="year"></span> <span class="name">Haneef Ur Rahman</span> · Built with ❤️ from Peshawar, Pakistan</p>
</footer>

<script>
  // Year
  document.getElementById('year').textContent = new Date().getFullYear();

  // Mobile menu
  const menuBtn = document.getElementById('menuBtn');
  const navLinks = document.getElementById('navLinks');
  menuBtn.addEventListener('click', () => navLinks.classList.toggle('open'));
  navLinks.querySelectorAll('a').forEach(a =>
    a.addEventListener('click', () => navLinks.classList.remove('open'))
  );

  // Reveal on scroll
  const observer = new IntersectionObserver(
    entries => entries.forEach(e => {
      if (e.isIntersecting) { e.target.classList.add('visible'); observer.unobserve(e.target); }
    }),
    { threshold: 0.1, rootMargin: '0px 0px -60px 0px' }
  );
  document.querySelectorAll('.reveal').forEach(el => observer.observe(el));

  // Nav background on scroll
  const nav = document.getElementById('nav');
  window.addEventListener('scroll', () => {
    nav.style.padding = window.scrollY > 20 ? '12px 0' : '16px 0';
  });
</script>

</body>
</html>
