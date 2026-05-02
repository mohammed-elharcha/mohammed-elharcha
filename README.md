<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
  <title>Mohamed El Harcha · Full Stack Dev Portfolio</title>
  <!-- Google Fonts + Smooth modern base -->
  <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,500;14..32,600;14..32,700&display=swap" rel="stylesheet">
  <!-- Font Awesome 6 (free icons, used for subtle icons instead of emoji) -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      background: #0B0F1A;  /* deep dark tech background */
      font-family: 'Inter', sans-serif;
      color: #EFF3FC;
      line-height: 1.5;
      padding: 2rem 1rem;
    }

    /* main card container - similar to modern github profile style */
    .gh-container {
      max-width: 1100px;
      margin: 0 auto;
      background: #0D1117;
      border-radius: 2rem;
      box-shadow: 0 25px 40px -12px rgba(0,0,0,0.6), 0 0 0 1px rgba(88, 166, 255, 0.08);
      overflow: hidden;
      transition: all 0.2s ease;
    }

    /* top subtle gradient line (design element from image feel) */
    .top-accent {
      height: 4px;
      background: linear-gradient(90deg, #3b82f6, #a855f7, #06b6d4);
      width: 100%;
    }

    /* inner spacing */
    .profile-content {
      padding: 2rem 2rem 2.5rem 2rem;
    }

    /* header area: name + tagline */
    .hero-header {
      text-align: center;
      margin-bottom: 2rem;
      border-bottom: 1px solid rgba(56, 68, 92, 0.5);
      padding-bottom: 1.5rem;
    }

    .hero-header h1 {
      font-size: 2.6rem;
      font-weight: 700;
      background: linear-gradient(135deg, #FFFFFF, #A0C4FF);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
      letter-spacing: -0.02em;
      margin-bottom: 0.5rem;
    }

    .badge-strip {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 1rem;
      margin-top: 0.75rem;
    }

    .view-badge {
      background: rgba(59, 130, 246, 0.12);
      backdrop-filter: blur(2px);
      padding: 0.3rem 1rem;
      border-radius: 60px;
      font-size: 0.85rem;
      font-weight: 500;
      border: 1px solid rgba(59, 130, 246, 0.25);
      color: #b9d0ff;
    }

    .tech-tagline {
      font-size: 1.2rem;
      font-weight: 500;
      background: linear-gradient(120deg, #E2E8F0, #94A3B8);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
      margin-top: 0.4rem;
      letter-spacing: -0.2px;
    }

    /* about me 2-col table style (no emoji, modern card split) */
    .about-grid {
      display: flex;
      flex-wrap: wrap;
      background: #0A0F16;
      border-radius: 1.5rem;
      margin: 2rem 0 2rem 0;
      border: 1px solid #1E2A3A;
      overflow: hidden;
    }

    .about-left {
      flex: 1;
      min-width: 200px;
      background: #0B1018;
      padding: 1.5rem 1.8rem;
      border-right: 1px solid #1E2A3A;
    }

    .about-right {
      flex: 2;
      padding: 1.5rem 1.8rem;
    }

    .about-item {
      display: flex;
      align-items: baseline;
      gap: 0.8rem;
      margin-bottom: 1rem;
      font-size: 1rem;
    }

    .about-icon {
      width: 28px;
      color: #3b82f6;
      font-size: 1.2rem;
      text-align: center;
    }

    .about-label {
      font-weight: 600;
      color: #CBD5E1;
      min-width: 100px;
    }

    .about-desc {
      color: #E2E8F0;
      font-weight: 400;
    }

    /* Skills section - icons row without emojis */
    .skills-section {
      margin: 2rem 0;
    }

    .section-title {
      font-size: 1.5rem;
      font-weight: 600;
      margin-bottom: 1.2rem;
      letter-spacing: -0.3px;
      display: flex;
      align-items: center;
      gap: 10px;
      border-left: 4px solid #3b82f6;
      padding-left: 1rem;
    }

    .skill-icons {
      background: #0A0F16;
      border-radius: 1.5rem;
      padding: 1.5rem 1rem;
      text-align: center;
      border: 1px solid #1E2A3A;
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 1.2rem;
    }

    .skill-icons img {
      height: 44px;
      width: auto;
      filter: drop-shadow(0 2px 4px rgba(0,0,0,0.3));
      transition: transform 0.2s ease;
    }

    .skill-icons img:hover {
      transform: translateY(-4px);
    }

    /* GitHub stats row */
    .stats-row {
      display: flex;
      flex-wrap: wrap;
      gap: 1.5rem;
      margin: 2rem 0;
      justify-content: center;
    }

    .stat-card {
      flex: 1;
      min-width: 240px;
      background: #0A0F16;
      border-radius: 1.2rem;
      padding: 0.8rem;
      text-align: center;
      border: 1px solid #1E2A3A;
      transition: all 0.2s;
    }

    .stat-card img {
      width: 100%;
      max-width: 400px;
      border-radius: 0.8rem;
    }

    /* Projects section - clean cards */
    .projects-grid {
      display: flex;
      flex-wrap: wrap;
      gap: 1.5rem;
      margin: 1.5rem 0 2rem;
    }

    .project-card {
      background: #0A0F16;
      border-radius: 1.2rem;
      border: 1px solid #1E2A3A;
      padding: 1.3rem;
      flex: 1 1 240px;
      transition: all 0.2s ease;
    }

    .project-card:hover {
      border-color: #3b82f6;
      transform: translateY(-3px);
    }

    .project-name {
      font-size: 1.25rem;
      font-weight: 700;
      margin-bottom: 0.5rem;
      color: white;
    }

    .project-tech {
      font-size: 0.75rem;
      font-family: monospace;
      background: #1E293B;
      display: inline-block;
      padding: 0.2rem 0.7rem;
      border-radius: 30px;
      margin: 0.5rem 0;
      color: #94A3B8;
    }

    .project-desc {
      font-size: 0.85rem;
      color: #B9C7D9;
      margin-top: 0.4rem;
    }

    /* Connect links */
    .connect-links {
      display: flex;
      justify-content: center;
      flex-wrap: wrap;
      gap: 1rem;
      margin: 2rem 0 1.5rem;
    }

    .btn-outline {
      background: transparent;
      border: 1px solid #2D3A4E;
      padding: 0.7rem 1.5rem;
      border-radius: 40px;
      font-weight: 500;
      display: inline-flex;
      align-items: center;
      gap: 10px;
      color: #EFF3FC;
      text-decoration: none;
      transition: all 0.2s;
      font-size: 0.9rem;
    }

    .btn-outline i {
      font-size: 1.1rem;
    }

    .btn-outline:hover {
      background: #1E2A3A;
      border-color: #3b82f6;
      color: white;
    }

    /* Mindset and fun corner sections (no emoji) */
    .mindset-block {
      background: #0A0F16;
      border-radius: 1.2rem;
      padding: 1.5rem;
      margin: 2rem 0 1.5rem;
      text-align: center;
      border: 1px solid #1E2A3A;
      font-style: normal;
    }

    .quote {
      font-size: 1rem;
      font-weight: 400;
      color: #B9C7D9;
      letter-spacing: -0.2px;
    }

    .fun-grid {
      display: flex;
      flex-wrap: wrap;
      justify-content: space-between;
      background: #0A0F16;
      border-radius: 1.2rem;
      padding: 1.2rem 1.5rem;
      margin: 1rem 0;
      border: 1px solid #1E2A3A;
      gap: 1rem;
    }

    .fun-item {
      display: flex;
      align-items: center;
      gap: 0.75rem;
      font-size: 0.9rem;
      color: #b9c7db;
    }

    .fun-item i {
      width: 24px;
      color: #3b82f6;
    }

    footer {
      text-align: center;
      margin-top: 2rem;
      font-size: 0.8rem;
      color: #5C6F8C;
      border-top: 1px solid #1E2A3A;
      padding-top: 1.5rem;
    }

    @media (max-width: 700px) {
      .profile-content {
        padding: 1.5rem;
      }
      .about-left {
        border-right: none;
        border-bottom: 1px solid #1E2A3A;
      }
      .hero-header h1 {
        font-size: 1.9rem;
      }
    }
  </style>
</head>
<body>
<div class="gh-container">
  <div class="top-accent"></div>
  <div class="profile-content">
    
    <!-- main header (no emoji) -->
    <div class="hero-header">
      <h1>Mohamed El Harcha</h1>
      <div class="badge-strip">
        <span class="view-badge"><i class="fas fa-eye" style="margin-right: 6px;"></i> Profile Views: 1.2k+</span>
        <span class="view-badge"><i class="fas fa-code"></i> Full Stack Developer</span>
      </div>
      <div class="tech-tagline">
        React • Node.js • Laravel • MongoDB
      </div>
    </div>
    
    <!-- About Me section (clean table-like style from design reference, no emojis) -->
    <div class="about-grid">
      <div class="about-left">
        <div class="about-item">
          <div class="about-icon"><i class="fas fa-graduation-cap"></i></div>
          <div class="about-label">Education</div>
          <div class="about-desc">Software Development Student – Morocco</div>
        </div>
        <div class="about-item">
          <div class="about-icon"><i class="fas fa-laptop-code"></i></div>
          <div class="about-label">Role</div>
          <div class="about-desc">Full Stack Developer</div>
        </div>
        <div class="about-item">
          <div class="about-icon"><i class="fas fa-brain"></i></div>
          <div class="about-label">Mindset</div>
          <div class="about-desc">Always learning & building</div>
        </div>
      </div>
      <div class="about-right">
        <div class="about-item">
          <div class="about-icon"><i class="fas fa-cogs"></i></div>
          <div class="about-label">Problem Solver</div>
          <div class="about-desc">Turn complex requirements into clean, functional code</div>
        </div>
        <div class="about-item">
          <div class="about-icon"><i class="fas fa-chart-line"></i></div>
          <div class="about-label">Currently Learning</div>
          <div class="about-desc">Next.js, DevOps, System Design</div>
        </div>
        <div class="about-item">
          <div class="about-icon"><i class="fas fa-bullseye"></i></div>
          <div class="about-label">Goal</div>
          <div class="about-desc">Professional Software Engineer – scalable web apps</div>
        </div>
      </div>
    </div>
    
    <!-- Skills: Languages & Tools (exactly like skillicons visual, but local fallback CDN) -->
    <div class="skills-section">
      <div class="section-title">
        <i class="fas fa-tools" style="font-size: 1.3rem;"></i> 
        <span>Languages & Tools</span>
      </div>
      <div class="skill-icons">
        <!-- using skill icons from official cdn (same reference style) -->
        <img src="https://skillicons.dev/icons?i=js" alt="JavaScript" />
        <img src="https://skillicons.dev/icons?i=ts" alt="TypeScript" />
        <img src="https://skillicons.dev/icons?i=php" alt="PHP" />
        <img src="https://skillicons.dev/icons?i=html" alt="HTML5" />
        <img src="https://skillicons.dev/icons?i=css" alt="CSS3" />
        <img src="https://skillicons.dev/icons?i=react" alt="React" />
        <img src="https://skillicons.dev/icons?i=tailwind" alt="Tailwind" />
        <img src="https://skillicons.dev/icons?i=nextjs" alt="Next.js" />
        <img src="https://skillicons.dev/icons?i=nodejs" alt="Node.js" />
        <img src="https://skillicons.dev/icons?i=express" alt="Express" />
        <img src="https://skillicons.dev/icons?i=laravel" alt="Laravel" />
        <img src="https://skillicons.dev/icons?i=mongodb" alt="MongoDB" />
        <img src="https://skillicons.dev/icons?i=mysql" alt="MySQL" />
        <img src="https://skillicons.dev/icons?i=git" alt="Git" />
        <img src="https://skillicons.dev/icons?i=github" alt="GitHub" />
        <img src="https://skillicons.dev/icons?i=vscode" alt="VSCode" />
        <img src="https://skillicons.dev/icons?i=docker" alt="Docker" />
      </div>
    </div>
    
    <!-- GitHub Analytics: stats cards with consistent design (removed emoji) -->
    <div class="stats-row">
      <div class="stat-card">
        <img src="https://github-readme-stats.vercel.app/api?username=mohammed-elharcha&show_icons=true&theme=tokyonight&hide_border=true&bg_color=0D1117&ring=3b82f6&icon_color=60a5fa" alt="GitHub Stats" />
      </div>
      <div class="stat-card">
        <img src="https://github-readme-streak-stats.herokuapp.com/?user=mohammed-elharcha&theme=tokyonight&hide_border=true&bg_color=0D1117&fire=3b82f6&ring=3b82f6" alt="GitHub Streak" />
      </div>
    </div>
    <div style="display: flex; justify-content: center; margin-top: 0.5rem;">
      <div class="stat-card" style="max-width: 460px;">
        <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=mohammed-elharcha&layout=compact&theme=tokyonight&hide_border=true&bg_color=0D1117" alt="Top Languages" />
      </div>
    </div>
    
    <!-- Featured projects (no emoji) -->
    <div class="skills-section">
      <div class="section-title">
        <i class="fas fa-rocket"></i>
        <span>Featured Projects</span>
      </div>
      <div class="projects-grid">
        <div class="project-card">
          <div class="project-name">Jouala</div>
          <div class="project-tech">React · Node.js · MongoDB</div>
          <div class="project-desc">Social media platform with real-time interactions and modern UI.</div>
        </div>
        <div class="project-card">
          <div class="project-name">E‑commerce App</div>
          <div class="project-tech">React · Express · MySQL</div>
          <div class="project-desc">Full stack online store with admin dashboard and cart system.</div>
        </div>
        <div class="project-card">
          <div class="project-name">School Management System</div>
          <div class="project-tech">Laravel · MySQL · Tailwind</div>
          <div class="project-desc">Manage students, teachers, classes, attendance & grades.</div>
        </div>
        <div class="project-card">
          <div class="project-name">Portfolio Website</div>
          <div class="project-tech">Next.js · Tailwind CSS</div>
          <div class="project-desc">Modern developer portfolio with light/dark performance.</div>
        </div>
      </div>
      <div style="font-size: 0.75rem; color: #5F7F9E; margin-top: 0.5rem; text-align: center;">
        <i class="fas fa-link"></i> Replace with actual project links when available
      </div>
    </div>
    
    <!-- Let's Connect: buttons with brand icons (no emoji) -->
    <div class="section-title">
      <i class="fas fa-address-card"></i>
      <span>Let's Connect</span>
    </div>
    <div class="connect-links">
      <a href="mailto:mohammed.elharcha.pro@gmail.com" class="btn-outline"><i class="fas fa-envelope"></i> Email</a>
      <a href="https://www.linkedin.com/in/mohammed-el-harcha-aa650b345/" target="_blank" class="btn-outline"><i class="fab fa-linkedin-in"></i> LinkedIn</a>
      <a href="https://github.com/mohammed-elharcha" target="_blank" class="btn-outline"><i class="fab fa-github"></i> GitHub</a>
    </div>
    
    <!-- Developer Mindset quote (no emoji, clean) -->
    <div class="mindset-block">
      <div class="quote">
        <i class="fas fa-quote-left" style="margin-right: 8px; color: #3b82f6;"></i> 
        “First solve the problem, then write the code, then make it better.”
      </div>
    </div>
    
    <!-- Fun Corner (grid style, no emoji, replaced by font awesome icons) -->
    <div class="section-title">
      <i class="fas fa-smile-wink"></i>
      <span>Fun Corner</span>
    </div>
    <div class="fun-grid">
      <div class="fun-item"><i class="fas fa-broom"></i> Clean code isn't written – it's rewritten</div>
      <div class="fun-item"><i class="fas fa-mug-hot"></i> Coffee + Code = Infinite loops of productivity</div>
      <div class="fun-item"><i class="fas fa-bug"></i> Bugs are just unpaid features</div>
      <div class="fun-item"><i class="fas fa-trophy"></i> Best error message is the one that never shows up</div>
    </div>
    
    <!-- closing signature -->
    <footer>
      <i class="fas fa-terminal"></i> "Code. Break. Fix. Learn. Repeat." 
      <span style="display: block; margin-top: 6px;">© Mohamed El Harcha — Full Stack Developer</span>
    </footer>
  </div>
</div>
</body>
</html>