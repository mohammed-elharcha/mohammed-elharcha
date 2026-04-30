<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Mohamed El Harcha — Profile</title>
  <link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;500;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet"/>
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --bg: #ffffff;
      --bg-secondary: #f5f5f3;
      --text-primary: #1a1a18;
      --text-secondary: #5f5e5a;
      --text-tertiary: #888780;
      --border: rgba(0,0,0,0.12);
      --border-hover: rgba(0,0,0,0.25);
      --radius-md: 8px;
      --radius-lg: 12px;
    }

    body {
      font-family: 'Syne', sans-serif;
      background: var(--bg);
      color: var(--text-primary);
      padding: 2.5rem 1.5rem;
      max-width: 720px;
      margin: 0 auto;
    }

    /* Hero */
    .hero {
      display: grid;
      grid-template-columns: auto 1fr;
      gap: 1.5rem;
      align-items: center;
      margin-bottom: 2.5rem;
    }
    .avatar {
      width: 80px;
      height: 80px;
      border-radius: 50%;
      background: linear-gradient(135deg, #185FA5, #0F6E56);
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 28px;
      font-weight: 700;
      color: #fff;
      flex-shrink: 0;
    }
    .hero-text h1 {
      font-size: 24px;
      font-weight: 500;
      margin-bottom: 4px;
    }
    .hero-text p {
      font-size: 13px;
      color: var(--text-secondary);
      font-family: 'JetBrains Mono', monospace;
      margin-bottom: 10px;
    }
    .badge-row { display: flex; flex-wrap: wrap; gap: 6px; }
    .badge {
      font-size: 11px;
      padding: 3px 10px;
      border-radius: 20px;
      font-weight: 500;
      background: var(--bg-secondary);
      color: var(--text-secondary);
      border: 0.5px solid var(--border);
    }
    .badge.blue  { background: #E6F1FB; color: #185FA5; }
    .badge.teal  { background: #E1F5EE; color: #0F6E56; }

    /* Sections */
    .section { margin-bottom: 2rem; }
    .section-label {
      font-size: 11px;
      font-weight: 500;
      letter-spacing: 0.08em;
      color: var(--text-tertiary);
      text-transform: uppercase;
      margin-bottom: 12px;
    }

    /* About grid */
    .about-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 8px; }
    .about-item {
      display: flex;
      gap: 8px;
      align-items: flex-start;
      font-size: 13px;
      color: var(--text-secondary);
      padding: 9px 12px;
      background: var(--bg-secondary);
      border-radius: var(--radius-md);
    }
    .about-icon { font-size: 14px; flex-shrink: 0; }

    /* Stack */
    .stack-group { display: flex; flex-direction: column; gap: 10px; }
    .stack-sub { font-size: 11px; color: var(--text-tertiary); margin-bottom: 5px; }
    .stack-row { display: flex; flex-wrap: wrap; gap: 6px; }
    .stack-tag {
      font-size: 12px;
      font-family: 'JetBrains Mono', monospace;
      padding: 4px 10px;
      border-radius: var(--radius-md);
      border: 0.5px solid var(--border);
      color: var(--text-secondary);
      background: var(--bg);
    }
    .stack-tag.lang  { border-color: #B5D4F4; color: #185FA5; background: #E6F1FB; }
    .stack-tag.front { border-color: #9FE1CB; color: #0F6E56; background: #E1F5EE; }
    .stack-tag.back  { border-color: #F5C4B3; color: #993C1D; background: #FAECE7; }
    .stack-tag.db    { border-color: #CECBF6; color: #534AB7; background: #EEEDFE; }
    .stack-tag.tool  { border-color: #D3D1C7; color: #5F5E5A; background: #F1EFE8; }

    /* Projects */
    .projects-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 8px; }
    .project-card {
      padding: 14px 16px;
      background: var(--bg);
      border: 0.5px solid var(--border);
      border-radius: var(--radius-lg);
      transition: border-color 0.15s;
    }
    .project-card:hover { border-color: var(--border-hover); }
    .project-name { font-size: 14px; font-weight: 500; margin-bottom: 4px; }
    .project-desc { font-size: 12px; color: var(--text-secondary); margin-bottom: 10px; }
    .project-tags { display: flex; gap: 4px; flex-wrap: wrap; }
    .project-tag {
      font-size: 10px;
      font-family: 'JetBrains Mono', monospace;
      padding: 2px 7px;
      border-radius: 10px;
      background: var(--bg-secondary);
      color: var(--text-tertiary);
    }

    /* Divider */
    .divider { height: 0.5px; background: var(--border); margin: 1.75rem 0; }

    /* Contact */
    .contact-row { display: flex; gap: 8px; flex-wrap: wrap; }
    .contact-btn {
      font-size: 13px;
      padding: 7px 16px;
      border-radius: var(--radius-md);
      border: 0.5px solid var(--border-hover);
      color: var(--text-secondary);
      background: var(--bg);
      text-decoration: none;
      transition: background 0.15s;
    }
    .contact-btn:hover { background: var(--bg-secondary); }

    /* Quote */
    .quote-block {
      padding: 12px 16px;
      border-left: 2px solid #378ADD;
      background: var(--bg-secondary);
      border-radius: 0 var(--radius-md) var(--radius-md) 0;
      font-size: 13px;
      color: var(--text-secondary);
      font-style: italic;
      font-family: 'JetBrains Mono', monospace;
    }

    /* Fun */
    .fun-row { display: flex; gap: 8px; flex-wrap: wrap; }
    .fun-pill {
      font-size: 12px;
      padding: 5px 12px;
      border-radius: 20px;
      background: var(--bg-secondary);
      color: var(--text-secondary);
      border: 0.5px solid var(--border);
    }

    @media (max-width: 520px) {
      .hero { grid-template-columns: 1fr; text-align: center; }
      .badge-row, .contact-row, .fun-row { justify-content: center; }
      .about-grid, .projects-grid { grid-template-columns: 1fr; }
    }
  </style>
</head>
<body>

  <!-- Hero -->
  <div class="hero">
    <div class="avatar">ME</div>
    <div class="hero-text">
      <h1>Mohamed El Harcha</h1>
      <p>Full Stack Web Developer</p>
      <div class="badge-row">
        <span class="badge blue">React</span>
        <span class="badge teal">Node.js</span>
        <span class="badge">Laravel</span>
        <span class="badge">MongoDB</span>
        <span class="badge">Morocco 🇲🇦</span>
      </div>
    </div>
  </div>

  <!-- About -->
  <div class="section">
    <div class="section-label">About</div>
    <div class="about-grid">
      <div class="about-item"><span class="about-icon">🎓</span><span>Software Dev Student, Morocco</span></div>
      <div class="about-item"><span class="about-icon">🌱</span><span>Learning Next.js, DevOps, System Design</span></div>
      <div class="about-item"><span class="about-icon">🎯</span><span>Goal: Scalable web engineering</span></div>
      <div class="about-item"><span class="about-icon">⚡</span><span>Problem solver &amp; product builder</span></div>
    </div>
  </div>

  <!-- Tech Stack -->
  <div class="section">
    <div class="section-label">Tech Stack</div>
    <div class="stack-group">
      <div>
        <div class="stack-sub">Languages</div>
        <div class="stack-row">
          <span class="stack-tag lang">JavaScript</span>
          <span class="stack-tag lang">TypeScript</span>
          <span class="stack-tag lang">PHP</span>
          <span class="stack-tag lang">HTML</span>
          <span class="stack-tag lang">CSS</span>
        </div>
      </div>
      <div>
        <div class="stack-sub">Frontend</div>
        <div class="stack-row">
          <span class="stack-tag front">React</span>
          <span class="stack-tag front">Next.js</span>
          <span class="stack-tag front">Tailwind CSS</span>
        </div>
      </div>
      <div>
        <div class="stack-sub">Backend</div>
        <div class="stack-row">
          <span class="stack-tag back">Node.js</span>
          <span class="stack-tag back">Express</span>
          <span class="stack-tag back">Laravel</span>
        </div>
      </div>
      <div>
        <div class="stack-sub">Databases</div>
        <div class="stack-row">
          <span class="stack-tag db">MongoDB</span>
          <span class="stack-tag db">MySQL</span>
        </div>
      </div>
      <div>
        <div class="stack-sub">Tools</div>
        <div class="stack-row">
          <span class="stack-tag tool">Git</span>
          <span class="stack-tag tool">GitHub</span>
          <span class="stack-tag tool">VS Code</span>
          <span class="stack-tag tool">Docker</span>
        </div>
      </div>
    </div>
  </div>

  <!-- Projects -->
  <div class="section">
    <div class="section-label">Featured Projects</div>
    <div class="projects-grid">
      <div class="project-card">
        <p class="project-name">Jouala</p>
        <p class="project-desc">Social media platform</p>
        <div class="project-tags">
          <span class="project-tag">React</span>
          <span class="project-tag">Node.js</span>
          <span class="project-tag">MongoDB</span>
        </div>
      </div>
      <div class="project-card">
        <p class="project-name">E-Commerce App</p>
        <p class="project-desc">Full stack store + admin dashboard</p>
        <div class="project-tags">
          <span class="project-tag">React</span>
          <span class="project-tag">Express</span>
        </div>
      </div>
      <div class="project-card">
        <p class="project-name">School Management</p>
        <p class="project-desc">Academic management system</p>
        <div class="project-tags">
          <span class="project-tag">Laravel</span>
          <span class="project-tag">MySQL</span>
        </div>
      </div>
      <div class="project-card">
        <p class="project-name">Portfolio</p>
        <p class="project-desc">Modern responsive dev portfolio</p>
        <div class="project-tags">
          <span class="project-tag">React</span>
          <span class="project-tag">Tailwind</span>
        </div>
      </div>
    </div>
  </div>

  <div class="divider"></div>

  <!-- Contact -->
  <div class="section">
    <div class="section-label">Contact</div>
    <div class="contact-row">
      <a class="contact-btn" href="mailto:mohammed.elharcha.pro@gmail.com">📧 Email</a>
      <a class="contact-btn" href="https://www.linkedin.com/in/mohammed-el-harcha-aa650b345/" target="_blank">💼 LinkedIn</a>
      <a class="contact-btn" href="https://github.com/mohammed-elharcha" target="_blank">🐙 GitHub</a>
    </div>
  </div>

  <!-- Quote -->
  <div class="section">
    <div class="quote-block">"First, solve the problem. Then, write the code. Then, make it better."</div>
  </div>

  <!-- Fun -->
  <div class="section">
    <div class="section-label">Fun</div>
    <div class="fun-row">
      <span class="fun-pill">Clean code is rewritten, not written</span>
      <span class="fun-pill">Coffee + Code = loops of productivity</span>
      <span class="fun-pill">Bugs are unpaid features 😄</span>
    </div>
  </div>

</body>
</html>
