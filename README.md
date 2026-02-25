<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Anirudh Rathore — AI Developer</title>
<link href="https://fonts.googleapis.com/css2?family=Barlow+Condensed:wght@100;200;300;400&family=DM+Sans:wght@300;400;500&family=DM+Mono:wght@300;400&display=swap" rel="stylesheet"/>
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --black: #0f0f0f;
    --white: #ffffff;
    --off-white: #f5f5f3;
    --orange: #F26522;
    --soft-green: #c8e8a0;
    --soft-peach: #f5c5a0;
    --soft-purple: #c4b0f5;
    --soft-blue: #a0d4f5;
    --gray: #888;
    --light-gray: #e8e8e6;
  }

  html { scroll-behavior: smooth; }

  body {
    font-family: 'DM Sans', sans-serif;
    background: var(--black);
    color: var(--white);
    cursor: none;
    overflow-x: hidden;
  }

  /* Custom cursor */
  .cursor {
    width: 10px; height: 10px;
    background: var(--orange);
    border-radius: 50%;
    position: fixed;
    pointer-events: none;
    z-index: 9999;
    transition: transform 0.15s ease;
    transform: translate(-50%, -50%);
  }
  .cursor-ring {
    width: 36px; height: 36px;
    border: 1.5px solid rgba(255,255,255,0.4);
    border-radius: 50%;
    position: fixed;
    pointer-events: none;
    z-index: 9998;
    transition: all 0.08s ease;
    transform: translate(-50%, -50%);
  }

  /* NAV */
  nav {
    position: fixed; top: 0; left: 0; right: 0;
    z-index: 100;
    display: flex; align-items: center; justify-content: space-between;
    padding: 0 32px;
    height: 64px;
    background: var(--black);
  }
  .nav-logo {
    display: flex; align-items: center; gap: 10px;
    font-family: 'DM Sans', sans-serif;
    font-weight: 500;
    font-size: 15px;
    letter-spacing: 0.05em;
    text-transform: uppercase;
  }
  .logo-mark {
    width: 34px; height: 34px;
    background: var(--orange);
    border-radius: 50%;
    display: flex; align-items: center; justify-content: center;
    font-weight: 700; font-size: 14px;
    color: white;
  }
  .nav-links {
    display: flex; gap: 0;
    background: rgba(255,255,255,0.08);
    border: 1px solid rgba(255,255,255,0.12);
    border-radius: 50px;
    padding: 6px 8px;
    list-style: none;
  }
  .nav-links a {
    color: rgba(255,255,255,0.7);
    text-decoration: none;
    font-size: 13px;
    font-weight: 400;
    padding: 7px 20px;
    border-radius: 50px;
    transition: all 0.2s;
    letter-spacing: 0.02em;
  }
  .nav-links a:hover {
    background: rgba(255,255,255,0.1);
    color: white;
  }
  .nav-cta {
    background: white;
    color: black !important;
    font-size: 12px !important;
    font-weight: 500 !important;
    padding: 10px 22px !important;
    border-radius: 50px;
    letter-spacing: 0.08em !important;
    text-transform: uppercase;
    text-decoration: none;
    transition: all 0.2s;
  }
  .nav-cta:hover { background: var(--orange) !important; color: white !important; }

  /* HERO */
  .hero {
    min-height: 100vh;
    background: var(--off-white);
    color: var(--black);
    padding: 64px 56px 56px;
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-template-rows: auto 1fr auto;
    gap: 0;
    position: relative;
    overflow: hidden;
  }

  .hero-headline {
    grid-column: 1;
    grid-row: 2;
    align-self: center;
    padding-right: 40px;
  }
  .hero-headline h1 {
    font-family: 'Barlow Condensed', sans-serif;
    font-weight: 200;
    font-size: clamp(80px, 10vw, 130px);
    line-height: 0.92;
    letter-spacing: 0.04em;
    text-transform: uppercase;
    color: var(--black);
  }
  .hero-headline h1 .line {
    display: block;
    opacity: 0;
    transform: translateY(30px);
    animation: slideUp 0.8s forwards;
  }
  .hero-headline h1 .line:nth-child(1) { animation-delay: 0.1s; }
  .hero-headline h1 .line:nth-child(2) { animation-delay: 0.25s; }
  .hero-headline h1 .line:nth-child(3) { animation-delay: 0.4s; }

  @keyframes slideUp {
    to { opacity: 1; transform: translateY(0); }
  }

  .hero-inline-badge {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    width: 90px; height: 90px;
    background: #fdf0e0;
    border-radius: 18px;
    font-size: 40px;
    margin-right: 10px;
    vertical-align: middle;
    margin-bottom: 8px;
    animation: popIn 0.5s 0.3s backwards;
  }
  @keyframes popIn {
    from { transform: scale(0.5) rotate(-10deg); opacity: 0; }
    to { transform: scale(1) rotate(0deg); opacity: 1; }
  }

  .hero-cta {
    display: flex;
    align-items: center;
    gap: 16px;
    margin-top: 48px;
    opacity: 0;
    animation: slideUp 0.6s 0.6s forwards;
  }
  .cta-btn {
    width: 52px; height: 52px;
    background: var(--black);
    border-radius: 50%;
    display: flex; align-items: center; justify-content: center;
    text-decoration: none;
    transition: all 0.3s;
    flex-shrink: 0;
  }
  .cta-btn:hover { background: var(--orange); transform: rotate(45deg); }
  .cta-btn svg { width: 20px; height: 20px; }
  .cta-label strong {
    display: block;
    font-size: 15px;
    font-weight: 500;
  }
  .cta-label span {
    font-size: 12px;
    color: var(--gray);
  }

  .hero-desc {
    grid-column: 1;
    grid-row: 3;
    padding-top: 24px;
    font-size: 14px;
    color: #555;
    max-width: 340px;
    line-height: 1.6;
    opacity: 0;
    animation: slideUp 0.6s 0.75s forwards;
  }

  /* Stacked cards visual */
  .hero-visual {
    grid-column: 2;
    grid-row: 1 / 4;
    position: relative;
    display: flex;
    align-items: center;
    justify-content: flex-end;
  }
  .card-stack {
    position: relative;
    width: 100%;
    height: 520px;
  }
  .stack-card {
    position: absolute;
    border-radius: 24px;
    animation: floatCard 0.8s backwards;
  }
  .stack-card:nth-child(1) {
    width: 85%; height: 88%;
    top: 0; right: -40px;
    background: var(--soft-green);
    animation-delay: 0.2s;
    transform: rotate(3deg);
  }
  .stack-card:nth-child(2) {
    width: 82%; height: 85%;
    top: 20px; right: -20px;
    background: var(--soft-peach);
    animation-delay: 0.35s;
    transform: rotate(1.5deg);
  }
  .stack-card:nth-child(3) {
    width: 80%; height: 83%;
    top: 40px; right: 0;
    background: linear-gradient(135deg, #c4b0f5 0%, #e0c4f5 30%, #f5c4e0 60%, #a0d4f5 100%);
    animation-delay: 0.5s;
    transform: rotate(0deg);
    overflow: hidden;
  }
  /* Wavy mesh inside card */
  .stack-card:nth-child(3)::after {
    content: '';
    position: absolute;
    bottom: -60px; left: -40px;
    width: 130%; height: 60%;
    background: linear-gradient(135deg, #6ee7ff 0%, #a78bfa 50%, #f472b6 100%);
    border-radius: 60% 40% 40% 60% / 60% 60% 40% 40%;
    opacity: 0.7;
    animation: waveMorph 6s ease-in-out infinite;
  }
  @keyframes waveMorph {
    0%, 100% { border-radius: 60% 40% 40% 60% / 60% 60% 40% 40%; transform: rotate(-2deg); }
    50% { border-radius: 40% 60% 60% 40% / 40% 40% 60% 60%; transform: rotate(2deg); }
  }

  /* Dot accent */
  .dot-accent {
    position: absolute;
    width: 18px; height: 18px;
    background: #1a1035;
    border-radius: 50%;
    top: 30px; right: 60px;
    z-index: 10;
    animation: floatDot 4s ease-in-out infinite;
  }
  @keyframes floatDot {
    0%, 100% { transform: translateY(0); }
    50% { transform: translateY(-12px); }
  }

  @keyframes floatCard {
    from { opacity: 0; transform: translateY(50px) rotate(0deg); }
    to { opacity: 1; }
  }

  /* SECTION SHARED */
  section {
    padding: 100px 56px;
  }
  .section-label {
    font-size: 11px;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--gray);
    margin-bottom: 48px;
    display: flex;
    align-items: center;
    gap: 12px;
  }
  .section-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: rgba(255,255,255,0.1);
    max-width: 80px;
  }

  /* SKILLS SECTION */
  #skills {
    background: var(--black);
    color: white;
  }
  .skills-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 2px;
  }
  .skill-cell {
    padding: 36px 32px;
    border: 1px solid rgba(255,255,255,0.06);
    transition: all 0.3s;
    position: relative;
    overflow: hidden;
  }
  .skill-cell::before {
    content: '';
    position: absolute;
    inset: 0;
    background: linear-gradient(135deg, rgba(242,101,34,0.06), transparent);
    opacity: 0;
    transition: opacity 0.3s;
  }
  .skill-cell:hover::before { opacity: 1; }
  .skill-cell:hover { border-color: rgba(242,101,34,0.3); }

  .skill-icon {
    font-size: 28px;
    margin-bottom: 16px;
  }
  .skill-cell h3 {
    font-family: 'Barlow Condensed', sans-serif;
    font-weight: 300;
    font-size: 28px;
    letter-spacing: 0.06em;
    text-transform: uppercase;
    margin-bottom: 10px;
  }
  .skill-cell p {
    font-size: 13px;
    color: rgba(255,255,255,0.4);
    line-height: 1.6;
  }
  .skill-tags {
    margin-top: 16px;
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
  }
  .skill-tag {
    font-size: 10px;
    font-family: 'DM Mono', monospace;
    letter-spacing: 0.06em;
    padding: 4px 10px;
    border: 1px solid rgba(255,255,255,0.15);
    border-radius: 50px;
    color: rgba(255,255,255,0.5);
  }

  /* EXPERIENCE */
  #experience {
    background: var(--off-white);
    color: var(--black);
  }
  #experience .section-label::after { background: rgba(0,0,0,0.1); }
  #experience .section-label { color: #999; }

  .exp-list { display: flex; flex-direction: column; }
  .exp-item {
    display: grid;
    grid-template-columns: 200px 1fr auto;
    gap: 40px;
    padding: 36px 0;
    border-bottom: 1px solid rgba(0,0,0,0.08);
    align-items: start;
    transition: all 0.3s;
    cursor: default;
  }
  .exp-item:hover { padding-left: 16px; }
  .exp-item:first-child { border-top: 1px solid rgba(0,0,0,0.08); }

  .exp-date {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    color: #888;
    padding-top: 4px;
  }
  .exp-role {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 32px;
    font-weight: 200;
    text-transform: uppercase;
    letter-spacing: 0.04em;
    line-height: 1;
    margin-bottom: 8px;
  }
  .exp-company {
    font-size: 12px;
    color: var(--orange);
    letter-spacing: 0.1em;
    text-transform: uppercase;
    font-weight: 500;
    margin-bottom: 12px;
  }
  .exp-desc {
    font-size: 13px;
    color: #555;
    line-height: 1.7;
    max-width: 480px;
  }
  .exp-badge {
    font-size: 10px;
    font-family: 'DM Mono', monospace;
    padding: 6px 14px;
    background: var(--black);
    color: white;
    border-radius: 50px;
    letter-spacing: 0.06em;
    text-transform: uppercase;
    white-space: nowrap;
  }

  /* PROJECTS */
  #projects {
    background: var(--black);
    color: white;
  }
  .projects-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 2px;
  }
  .project-card {
    padding: 48px 40px;
    background: rgba(255,255,255,0.025);
    border: 1px solid rgba(255,255,255,0.05);
    transition: all 0.3s;
    position: relative;
    overflow: hidden;
  }
  .project-card:hover {
    background: rgba(255,255,255,0.05);
    border-color: rgba(255,255,255,0.12);
  }
  .project-card:hover .project-arrow { transform: rotate(45deg) translate(2px, -2px); }
  .project-num {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    color: var(--orange);
    letter-spacing: 0.1em;
    margin-bottom: 24px;
  }
  .project-title {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 42px;
    font-weight: 200;
    text-transform: uppercase;
    letter-spacing: 0.04em;
    line-height: 0.95;
    margin-bottom: 20px;
  }
  .project-desc {
    font-size: 13px;
    color: rgba(255,255,255,0.45);
    line-height: 1.7;
    margin-bottom: 28px;
  }
  .project-footer {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
  .project-stack {
    display: flex; gap: 8px; flex-wrap: wrap;
  }
  .project-stack span {
    font-size: 10px;
    font-family: 'DM Mono', monospace;
    padding: 3px 9px;
    border: 1px solid rgba(255,255,255,0.12);
    border-radius: 3px;
    color: rgba(255,255,255,0.4);
  }
  .project-arrow {
    width: 36px; height: 36px;
    border: 1px solid rgba(255,255,255,0.15);
    border-radius: 50%;
    display: flex; align-items: center; justify-content: center;
    transition: all 0.3s;
    flex-shrink: 0;
  }
  .project-arrow svg { width: 14px; height: 14px; opacity: 0.5; }

  /* PUBLICATIONS */
  #publications {
    background: var(--off-white);
    color: var(--black);
  }
  #publications .section-label::after { background: rgba(0,0,0,0.1); }
  #publications .section-label { color: #999; }
  .pub-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 2px;
  }
  .pub-card {
    padding: 36px 30px;
    border: 1px solid rgba(0,0,0,0.07);
    background: white;
    transition: all 0.3s;
  }
  .pub-card:hover { transform: translateY(-4px); box-shadow: 0 20px 40px rgba(0,0,0,0.08); }
  .pub-icon {
    font-size: 32px;
    margin-bottom: 20px;
  }
  .pub-card h3 {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 22px;
    font-weight: 300;
    text-transform: uppercase;
    letter-spacing: 0.04em;
    margin-bottom: 10px;
  }
  .pub-card p {
    font-size: 12px;
    color: #777;
    line-height: 1.6;
  }

  /* CONTACT */
  #contact {
    background: var(--black);
    color: white;
    text-align: center;
    padding: 120px 56px;
  }
  .contact-headline {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: clamp(60px, 8vw, 100px);
    font-weight: 200;
    text-transform: uppercase;
    letter-spacing: 0.06em;
    line-height: 0.95;
    margin-bottom: 48px;
  }
  .contact-headline em {
    font-style: normal;
    color: var(--orange);
  }
  .contact-links {
    display: flex;
    justify-content: center;
    gap: 16px;
    flex-wrap: wrap;
  }
  .contact-link {
    display: flex; align-items: center; gap: 10px;
    font-size: 12px;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    text-decoration: none;
    padding: 14px 28px;
    border: 1px solid rgba(255,255,255,0.15);
    border-radius: 50px;
    color: white;
    transition: all 0.3s;
    font-family: 'DM Sans', sans-serif;
  }
  .contact-link:hover { background: var(--orange); border-color: var(--orange); }

  /* Footer */
  footer {
    background: var(--black);
    border-top: 1px solid rgba(255,255,255,0.06);
    padding: 24px 56px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    font-size: 11px;
    color: rgba(255,255,255,0.25);
    letter-spacing: 0.08em;
    text-transform: uppercase;
  }

  /* Responsive */
  @media (max-width: 900px) {
    .hero { grid-template-columns: 1fr; padding: 80px 24px 40px; }
    .hero-visual { display: none; }
    nav { padding: 0 20px; }
    .nav-links { display: none; }
    section { padding: 60px 24px; }
    .skills-grid, .projects-grid, .pub-grid { grid-template-columns: 1fr; }
    .exp-item { grid-template-columns: 1fr; gap: 8px; }
    footer { flex-direction: column; gap: 8px; text-align: center; }
  }
</style>
</head>
<body>

<div class="cursor" id="cursor"></div>
<div class="cursor-ring" id="cursorRing"></div>

<!-- NAV -->
<nav>
  <div class="nav-logo">
    <div class="logo-mark">A</div>
    Anirudh Rathore
  </div>
  <ul class="nav-links">
    <li><a href="#skills">Skills</a></li>
    <li><a href="#experience">Experience</a></li>
    <li><a href="#projects">Projects</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
  <a href="mailto:anirudhrathore0713@gmail.com" class="nav-cta">Let's Talk</a>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="hero-headline">
    <h1>
      <span class="line">I BUILD</span>
      <span class="line"><span class="hero-inline-badge">🤖</span> INTELLIGENT</span>
      <span class="line">SYSTEMS</span>
    </h1>
    <div class="hero-cta">
      <a href="#projects" class="cta-btn">
        <svg viewBox="0 0 24 24" fill="none" stroke="white" stroke-width="2">
          <path d="M7 17L17 7M17 7H7M17 7v10"/>
        </svg>
      </a>
      <div class="cta-label">
        <strong>View My Work</strong>
        <span>ML · Vision · RAG · SaaS</span>
      </div>
    </div>
  </div>
  <p class="hero-desc">
    Data Scientist & AI Developer with 2.5+ years building production-grade ML systems, 
    computer vision models, and intelligent SaaS platforms. Currently pursuing MSc AI at 
    Heriot-Watt University, Dubai.
  </p>
  <div class="hero-visual">
    <div class="dot-accent"></div>
    <div class="card-stack">
      <div class="stack-card"></div>
      <div class="stack-card"></div>
      <div class="stack-card"></div>
    </div>
  </div>
</section>

<!-- SKILLS -->
<section id="skills">
  <div class="section-label">Skills & Stack</div>
  <div class="skills-grid">
    <div class="skill-cell">
      <div class="skill-icon">🧠</div>
      <h3>Machine Learning</h3>
      <p>Deep learning architectures, CNNs, hyperparameter tuning, and model evaluation at production scale.</p>
      <div class="skill-tags">
        <span class="skill-tag">TensorFlow</span>
        <span class="skill-tag">PyTorch</span>
        <span class="skill-tag">Scikit-Learn</span>
        <span class="skill-tag">CNNs</span>
      </div>
    </div>
    <div class="skill-cell">
      <div class="skill-icon">👁️</div>
      <h3>Computer Vision</h3>
      <p>Image-based models, handwriting recognition, crop disease detection, and real-time CV pipelines.</p>
      <div class="skill-tags">
        <span class="skill-tag">OpenCV</span>
        <span class="skill-tag">F1-Score</span>
        <span class="skill-tag">Precision</span>
        <span class="skill-tag">Recall</span>
      </div>
    </div>
    <div class="skill-cell">
      <div class="skill-icon">💬</div>
      <h3>NLP & RAG</h3>
      <p>Retrieval-Augmented Generation pipelines, conversational AI concierges, and LLM integrations.</p>
      <div class="skill-tags">
        <span class="skill-tag">AWS Bedrock</span>
        <span class="skill-tag">RAG</span>
        <span class="skill-tag">NLP</span>
        <span class="skill-tag">LLMs</span>
      </div>
    </div>
    <div class="skill-cell">
      <div class="skill-icon">☁️</div>
      <h3>Cloud & DevOps</h3>
      <p>CI/CD pipelines, containerized deployments, Redis caching, and multi-tenant SaaS architecture.</p>
      <div class="skill-tags">
        <span class="skill-tag">AWS EC2</span>
        <span class="skill-tag">Azure</span>
        <span class="skill-tag">Docker</span>
        <span class="skill-tag">CI/CD</span>
      </div>
    </div>
    <div class="skill-cell">
      <div class="skill-icon">🗄️</div>
      <h3>Databases</h3>
      <p>PostgreSQL with Row-Level Security, MongoDB, Firebase real-time sync, and Redis-first strategies.</p>
      <div class="skill-tags">
        <span class="skill-tag">PostgreSQL</span>
        <span class="skill-tag">MongoDB</span>
        <span class="skill-tag">Firebase</span>
        <span class="skill-tag">Redis</span>
      </div>
    </div>
    <div class="skill-cell">
      <div class="skill-icon">📱</div>
      <h3>App & Web Dev</h3>
      <p>Cross-platform mobile apps, data-driven backends, and published author on Flutter development.</p>
      <div class="skill-tags">
        <span class="skill-tag">Flutter</span>
        <span class="skill-tag">Dart</span>
        <span class="skill-tag">TypeScript</span>
        <span class="skill-tag">SQL</span>
      </div>
    </div>
  </div>
</section>

<!-- EXPERIENCE -->
<section id="experience">
  <div class="section-label">Experience</div>
  <div class="exp-list">
    <div class="exp-item">
      <div class="exp-date">Jun 2025 – Present</div>
      <div>
        <div class="exp-role">Lead AI Developer<br/>& Product Manager</div>
        <div class="exp-company">VirtueCloud — India</div>
        <p class="exp-desc">Engineered a conversational AI Concierge using AWS Bedrock with a custom RAG pipeline achieving 99% accuracy. Managed CI/CD on AWS EC2 with Redis-first caching. Directed end-to-end development of a multi-tenant SaaS platform with PostgreSQL RLS for enterprise data isolation.</p>
      </div>
      <span class="exp-badge">Current</span>
    </div>
    <div class="exp-item">
      <div class="exp-date">Apr 2023 – Sep 2025</div>
      <div>
        <div class="exp-role">Application &<br/>Web Developer</div>
        <div class="exp-company">Various Clients — Remote</div>
        <p class="exp-desc">Built and launched data-driven cross-platform applications with Firebase real-time sync. Developed inventory tracking systems managing 10,000+ SKUs for clients including Hyginiee, Pooja Copy House, and MLB College.</p>
      </div>
      <span class="exp-badge">Contract</span>
    </div>
    <div class="exp-item">
      <div class="exp-date">Jun 2022 – Jan 2023</div>
      <div>
        <div class="exp-role">AI Developer<br/>Computer Vision</div>
        <div class="exp-company">TCS — Indore, India</div>
        <p class="exp-desc">Developed a CV-based handwriting detection model using Python and TensorFlow with 99% accuracy. Implemented self-learning capabilities for continuous retraining, boosting task accuracy by 30% across integrated cross-platform apps.</p>
      </div>
      <span class="exp-badge">Full-time</span>
    </div>
  </div>
</section>

<!-- PROJECTS -->
<section id="projects">
  <div class="section-label">Selected Projects</div>
  <div class="projects-grid">
    <div class="project-card">
      <div class="project-num">01</div>
      <div class="project-title">Crop Disease<br/>Prediction</div>
      <p class="project-desc">Deep learning model diagnosing crop diseases from image and soil data. Built CNN architecture from scratch with learning rate scheduling, dropout regularisation, and a robust Python backend deployment.</p>
      <div class="project-footer">
        <div class="project-stack">
          <span>PyTorch</span><span>TensorFlow</span><span>CNN</span><span>Python</span>
        </div>
        <div class="project-arrow">
          <svg viewBox="0 0 24 24" fill="none" stroke="white" stroke-width="2">
            <path d="M7 17L17 7M17 7H7M17 7v10"/>
          </svg>
        </div>
      </div>
    </div>
    <div class="project-card">
      <div class="project-num">02</div>
      <div class="project-title">AI Concierge<br/>RAG System</div>
      <p class="project-desc">Production conversational AI for hotel guest services and automated ticketing. Custom Retrieval-Augmented Generation pipeline on AWS Bedrock achieving 99% accuracy with Redis-first caching for ultra-low latency.</p>
      <div class="project-footer">
        <div class="project-stack">
          <span>AWS Bedrock</span><span>RAG</span><span>Redis</span><span>PostgreSQL</span>
        </div>
        <div class="project-arrow">
          <svg viewBox="0 0 24 24" fill="none" stroke="white" stroke-width="2">
            <path d="M7 17L17 7M17 7H7M17 7v10"/>
          </svg>
        </div>
      </div>
    </div>
    <div class="project-card">
      <div class="project-num">03</div>
      <div class="project-title">Handwriting<br/>Recognition</div>
      <p class="project-desc">Computer vision model that reads text from handwritten images. Features self-learning capabilities with continuous retraining on user samples. Research published in the Journal of Maharaja Sayajirao University.</p>
      <div class="project-footer">
        <div class="project-stack">
          <span>TensorFlow</span><span>OpenCV</span><span>Python</span><span>Research</span>
        </div>
        <div class="project-arrow">
          <svg viewBox="0 0 24 24" fill="none" stroke="white" stroke-width="2">
            <path d="M7 17L17 7M17 7H7M17 7v10"/>
          </svg>
        </div>
      </div>
    </div>
    <div class="project-card">
      <div class="project-num">04</div>
      <div class="project-title">Inventory<br/>Management App</div>
      <p class="project-desc">Cross-platform production tracking app managing 10,000+ SKUs with real-time database synchronisation. Deployed for Hyginiee and other clients with scalable Firebase backend infrastructure.</p>
      <div class="project-footer">
        <div class="project-stack">
          <span>Flutter</span><span>Firebase</span><span>Dart</span><span>Real-time DB</span>
        </div>
        <div class="project-arrow">
          <svg viewBox="0 0 24 24" fill="none" stroke="white" stroke-width="2">
            <path d="M7 17L17 7M17 7H7M17 7v10"/>
          </svg>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- PUBLICATIONS -->
<section id="publications">
  <div class="section-label">Publications & Credentials</div>
  <div class="pub-grid">
    <div class="pub-card">
      <div class="pub-icon">📰</div>
      <h3>Research Paper</h3>
      <p>"Recognition of Handwritten Characters" — Published in the Journal of The Maharaja Sayajirao University of Baroda.</p>
    </div>
    <div class="pub-card">
      <div class="pub-icon">📘</div>
      <h3>Authored Book</h3>
      <p>"Application Development using Flutter" — Full-length technical book on cross-platform mobile development.</p>
    </div>
    <div class="pub-card">
      <div class="pub-icon">🎓</div>
      <h3>MSc AI</h3>
      <p>Currently pursuing Master of Artificial Intelligence at Heriot-Watt University, Dubai (2025–2026).</p>
    </div>
    <div class="pub-card">
      <div class="pub-icon">🏅</div>
      <h3>IBM Data Analytics</h3>
      <p>IBM Data Analytics Professional Certificate via Coursera. Foundations in data analysis and visualisation.</p>
    </div>
    <div class="pub-card">
      <div class="pub-icon">🎨</div>
      <h3>Google UX Design</h3>
      <p>Google Foundations of User Experience (UX) Design certification — bridging AI with human-centred design.</p>
    </div>
    <div class="pub-card">
      <div class="pub-icon">⚡</div>
      <h3>99% Accuracy</h3>
      <p>Achieved 99% model accuracy in both TCS handwriting recognition and VirtueCloud AI Concierge deployments.</p>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <div class="contact-headline">
    LET'S BUILD<br/>SOMETHING <em>INTELLIGENT</em><br/>TOGETHER
  </div>
  <div class="contact-links">
    <a href="mailto:anirudhrathore0713@gmail.com" class="contact-link">
      <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="2" y="4" width="20" height="16" rx="2"/><path d="m22 7-8.97 5.7a1.94 1.94 0 0 1-2.06 0L2 7"/></svg>
      Email
    </a>
    <a href="https://linkedin.com" class="contact-link" target="_blank">
      <svg width="14" height="14" viewBox="0 0 24 24" fill="currentColor"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"/><rect x="2" y="9" width="4" height="12"/><circle cx="4" cy="4" r="2"/></svg>
      LinkedIn
    </a>
    <a href="https://github.com" class="contact-link" target="_blank">
      <svg width="14" height="14" viewBox="0 0 24 24" fill="currentColor"><path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"/></svg>
      GitHub
    </a>
    <a href="#" class="contact-link">
      <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="10"/><line x1="2" y1="12" x2="22" y2="12"/><path d="M12 2a15.3 15.3 0 0 1 4 10 15.3 15.3 0 0 1-4 10 15.3 15.3 0 0 1-4-10 15.3 15.3 0 0 1 4-10z"/></svg>
      Portfolio
    </a>
  </div>
</section>

<footer>
  <span>© 2026 Anirudh Rathore</span>
  <span>Dubai, UAE 🇦🇪</span>
  <span>AI Developer · Data Scientist</span>
</footer>

<script>
  // Cursor tracking
  const cursor = document.getElementById('cursor');
  const ring = document.getElementById('cursorRing');
  let mx = 0, my = 0, rx = 0, ry = 0;
  document.addEventListener('mousemove', e => {
    mx = e.clientX; my = e.clientY;
    cursor.style.left = mx + 'px';
    cursor.style.top = my + 'px';
  });
  function animRing() {
    rx += (mx - rx) * 0.12;
    ry += (my - ry) * 0.12;
    ring.style.left = rx + 'px';
    ring.style.top = ry + 'px';
    requestAnimationFrame(animRing);
  }
  animRing();

  // Cursor scale on hover
  document.querySelectorAll('a, button, .skill-cell, .project-card, .exp-item').forEach(el => {
    el.addEventListener('mouseenter', () => {
      cursor.style.transform = 'translate(-50%,-50%) scale(2.5)';
      ring.style.transform = 'translate(-50%,-50%) scale(1.4)';
    });
    el.addEventListener('mouseleave', () => {
      cursor.style.transform = 'translate(-50%,-50%) scale(1)';
      ring.style.transform = 'translate(-50%,-50%) scale(1)';
    });
  });

  // Scroll reveal
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        e.target.style.opacity = '1';
        e.target.style.transform = 'translateY(0)';
      }
    });
  }, { threshold: 0.1 });

  document.querySelectorAll('.skill-cell, .project-card, .pub-card, .exp-item').forEach((el, i) => {
    el.style.opacity = '0';
    el.style.transform = 'translateY(24px)';
    el.style.transition = `opacity 0.5s ${i * 0.07}s, transform 0.5s ${i * 0.07}s`;
    observer.observe(el);
  });
</script>
</body>
</html>
