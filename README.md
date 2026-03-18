<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Mohan Dhass G — GitHub Profile</title>
  <style>
    * { box-sizing: border-box; margin: 0; padding: 0; }
    body { font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif; background: #f6f8fa; display: flex; justify-content: center; padding: 2rem 1rem; }

    /* ── Keyframe Animations ── */
    @keyframes fadeSlideDown {
      from { opacity: 0; transform: translateY(-24px); }
      to   { opacity: 1; transform: translateY(0); }
    }
    @keyframes fadeSlideUp {
      from { opacity: 0; transform: translateY(20px); }
      to   { opacity: 1; transform: translateY(0); }
    }
    @keyframes fadeIn {
      from { opacity: 0; }
      to   { opacity: 1; }
    }
    @keyframes wave {
      0%   { transform: rotate(0deg); }
      20%  { transform: rotate(20deg); }
      40%  { transform: rotate(-10deg); }
      60%  { transform: rotate(20deg); }
      80%  { transform: rotate(-5deg); }
      100% { transform: rotate(0deg); }
    }
    @keyframes badgePop {
      from { opacity: 0; transform: scale(0.8); }
      to   { opacity: 1; transform: scale(1); }
    }
    @keyframes shimmer {
      0%   { background-position: -200% center; }
      100% { background-position: 200% center; }
    }
    @keyframes pulse {
      0%, 100% { box-shadow: 0 0 0 0 rgba(180,220,160,0.7); }
      50%       { box-shadow: 0 0 0 8px rgba(180,220,160,0); }
    }
    @keyframes rowFade {
      from { opacity: 0; transform: translateX(-12px); }
      to   { opacity: 1; transform: translateX(0); }
    }

    .profile-wrap {
      max-width: 860px; width: 100%;
      animation: fadeIn 0.5s ease both;
    }

    /* ── Header ── */
    .wave-top {
      background: linear-gradient(135deg, #DCF0D3, #b8e0a8);
      border-radius: 12px 12px 0 0;
      padding: 2.5rem 2rem 2rem;
      text-align: center;
      color: #2d5a1b;
      animation: fadeSlideDown 0.7s cubic-bezier(0.22,1,0.36,1) both;
      position: relative;
      overflow: hidden;
    }
    .wave-top::after {
      content: '';
      position: absolute;
      inset: 0;
      background: linear-gradient(100deg, transparent 30%, rgba(255,255,255,0.4) 50%, transparent 70%);
      background-size: 200% 100%;
      animation: shimmer 3.5s linear infinite;
      pointer-events: none;
    }
    .wave-top h1 {
      font-size: 26px; font-weight: 600; margin-bottom: 6px;
      animation: fadeSlideDown 0.8s 0.1s cubic-bezier(0.22,1,0.36,1) both;
    }
    .wave-emoji {
      display: inline-block;
      animation: wave 1.8s 1s ease-in-out;
      transform-origin: 70% 80%;
    }
    .wave-top p {
      font-size: 14px; opacity: 0.75; margin-bottom: 1.25rem;
      animation: fadeSlideDown 0.8s 0.2s cubic-bezier(0.22,1,0.36,1) both;
    }

    /* ── Social Badges ── */
    .social-links {
      display: flex; flex-wrap: wrap; gap: 8px; justify-content: center;
      animation: fadeIn 0.8s 0.4s both;
    }
    .badge {
      display: inline-flex; align-items: center; gap: 6px;
      padding: 6px 14px; border-radius: 6px;
      font-size: 12px; font-weight: 500; letter-spacing: 0.5px;
      text-decoration: none; color: white;
      transition: transform 0.18s ease, opacity 0.18s ease;
    }
    .badge:hover { transform: translateY(-2px); opacity: 0.88; }
    .badge svg { width: 14px; height: 14px; fill: white; flex-shrink: 0; }
    .b-linkedin  { background: #0077b5; }
    .b-github    { background: #181717; }
    .b-portfolio { background: #3a7a22; }
    .b-gmail     { background: #d14836; }

    /* ── Content Area ── */
    .content {
      background: #fff;
      border: 1px solid #c8e0be;
      border-top: none;
      border-radius: 0 0 12px 12px;
      padding: 1.75rem 2rem;
      animation: fadeSlideUp 0.7s 0.3s cubic-bezier(0.22,1,0.36,1) both;
    }

    .section { margin-bottom: 1.75rem; }
    .section-title {
      font-size: 15px; font-weight: 600; color: #24292f;
      margin-bottom: 0.75rem;
      display: flex; align-items: center; gap: 8px;
    }
    .group-label { font-size: 12px; color: #57606a; margin-bottom: 8px; margin-top: 12px; }
    .tech-badges { display: flex; flex-wrap: wrap; gap: 6px; }

    .tech-badge {
      display: inline-flex; align-items: center; gap: 5px;
      padding: 5px 10px; border-radius: 6px;
      font-size: 11.5px; font-weight: 500; color: white; letter-spacing: 0.3px;
      text-decoration: none;
      opacity: 0;
      animation: badgePop 0.4s ease forwards;
      transition: transform 0.15s ease, filter 0.15s ease;
    }
    .tech-badge:hover { transform: translateY(-2px) scale(1.04); filter: brightness(1.12); }
    .tech-badge img { width: 14px; height: 14px; }

    .tech-badges .tech-badge:nth-child(1) { animation-delay: 0.55s; }
    .tech-badges .tech-badge:nth-child(2) { animation-delay: 0.65s; }
    .tech-badges .tech-badge:nth-child(3) { animation-delay: 0.75s; }
    .tech-badges .tech-badge:nth-child(4) { animation-delay: 0.85s; }
    .tech-badges .tech-badge:nth-child(5) { animation-delay: 0.95s; }
    .tech-badges .tech-badge:nth-child(6) { animation-delay: 1.05s; }
    .tech-badges .tech-badge:nth-child(7) { animation-delay: 1.15s; }

    .divider { height: 1px; background: #c8e0be; margin: 1.5rem 0; }

    /* ── Projects Table ── */
    .projects-table { width: 100%; border-collapse: collapse; font-size: 13.5px; }
    .projects-table th {
      text-align: left; font-weight: 500; font-size: 12px; color: #57606a;
      padding: 0 12px 8px 0; border-bottom: 1px solid #c8e0be;
    }
    .projects-table td {
      padding: 10px 12px 10px 0; vertical-align: top;
      border-bottom: 1px solid #c8e0be; color: #24292f;
      opacity: 0;
      animation: rowFade 0.5s ease forwards;
    }
    .projects-table tr:last-child td { border-bottom: none; }
    .projects-table tr:nth-child(1) td { animation-delay: 0.9s; }
    .projects-table tr:nth-child(2) td { animation-delay: 1.1s; }
    .projects-table tr:nth-child(3) td { animation-delay: 1.3s; }
    .projects-table tr { transition: background 0.15s ease; }
    .projects-table tr:hover td { background: #f2faed; }

    .proj-name { font-weight: 500; margin-bottom: 3px; }
    .proj-desc { font-size: 12.5px; color: #57606a; line-height: 1.5; }
    .link-badges { display: flex; gap: 6px; flex-wrap: wrap; margin-top: 6px; }
    .link-badge {
      display: inline-flex; align-items: center; gap: 4px;
      padding: 3px 9px; border-radius: 5px;
      font-size: 11px; font-weight: 500; text-decoration: none; color: white;
      transition: transform 0.15s ease, opacity 0.15s ease;
    }
    .link-badge:hover { transform: translateY(-1px); opacity: 0.85; }
    .lb-repo { background: #181717; }
    .lb-live { background: #3aad6e; }

    .view-all {
      font-size: 13px; font-weight: 500; color: #3a7a22;
      text-decoration: none; display: inline-flex; align-items: center; gap: 4px;
      margin-top: 1rem;
      transition: gap 0.2s ease;
      animation: fadeIn 1s 1.5s both;
    }
    .view-all:hover { text-decoration: underline; gap: 8px; }

    /* ── Footer ── */
    .wave-bottom {
      background: linear-gradient(135deg, #b8e0a8, #DCF0D3);
      border-radius: 0 0 12px 12px;
      height: 50px;
      animation: pulse 3s 1.5s ease-in-out infinite;
    }
  </style>
</head>
<body>
<div class="profile-wrap">

  <div class="wave-top">
    <h1>Hi, I'm Mohan Dhass G <span class="wave-emoji">👋</span></h1>
    <p>Full Stack Developer &nbsp;·&nbsp; Karur, India</p>
    <div class="social-links">
      <a href="https://www.linkedin.com/in/mohandhassg05/" class="badge b-linkedin" target="_blank">
        <svg viewBox="0 0 24 24"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
        LinkedIn
      </a>
      <a href="https://github.com/gkdhass" class="badge b-github" target="_blank">
        <svg viewBox="0 0 24 24"><path d="M12 .297c-6.63 0-12 5.373-12 12 0 5.303 3.438 9.8 8.205 11.385.6.113.82-.258.82-.577 0-.285-.01-1.04-.015-2.04-3.338.724-4.042-1.61-4.042-1.61C4.422 18.07 3.633 17.7 3.633 17.7c-1.087-.744.084-.729.084-.729 1.205.084 1.838 1.236 1.838 1.236 1.07 1.835 2.809 1.305 3.495.998.108-.776.417-1.305.76-1.605-2.665-.3-5.466-1.332-5.466-5.93 0-1.31.465-2.38 1.235-3.22-.135-.303-.54-1.523.105-3.176 0 0 1.005-.322 3.3 1.23.96-.267 1.98-.399 3-.405 1.02.006 2.04.138 3 .405 2.28-1.552 3.285-1.23 3.285-1.23.645 1.653.24 2.873.12 3.176.765.84 1.23 1.91 1.23 3.22 0 4.61-2.805 5.625-5.475 5.92.42.36.81 1.096.81 2.22 0 1.606-.015 2.896-.015 3.286 0 .315.21.69.825.57C20.565 22.092 24 17.592 24 12.297c0-6.627-5.373-12-12-12"/></svg>
        GitHub
      </a>
      <a href="https://mohandhass.vercel.app/" class="badge b-portfolio" target="_blank">
        <svg viewBox="0 0 24 24" fill="white"><path d="M12 2C6.477 2 2 6.477 2 12s4.477 10 10 10 10-4.477 10-10S17.523 2 12 2zm6.918 6h-2.65a15.8 15.8 0 00-1.395-3.607A8.033 8.033 0 0118.918 8zM12 4.041c.95 1.268 1.701 2.855 2.138 3.959H9.862C10.299 6.896 11.05 5.309 12 4.041zM4.262 14a7.957 7.957 0 010-4h3.035a16.513 16.513 0 000 4H4.262zm.82 2h2.65c.326 1.3.815 2.527 1.395 3.607A8.032 8.032 0 015.082 16zm2.65-8H5.082a8.032 8.032 0 014.045-3.607A15.8 15.8 0 007.732 8zM12 19.959c-.95-1.268-1.701-2.855-2.138-3.959h4.276c-.437 1.104-1.188 2.691-2.138 3.959zM14.297 14H9.703a14.522 14.522 0 010-4h4.594a14.522 14.522 0 010 4zm.245 5.607A15.8 15.8 0 0015.937 16h2.65a8.033 8.033 0 01-4.045 3.607zM15.938 14a16.513 16.513 0 000-4h3.035a7.957 7.957 0 010 4H15.938z"/></svg>
        Portfolio
      </a>
      <a href="mailto:mohandhassgovind@gmail.com" class="badge b-gmail">
        <svg viewBox="0 0 24 24"><path d="M24 5.457v13.909c0 .904-.732 1.636-1.636 1.636h-3.819V11.73L12 16.64l-6.545-4.91v9.273H1.636A1.636 1.636 0 010 19.366V5.457c0-2.023 2.309-3.178 3.927-1.964L5.455 4.64 12 9.548l6.545-4.91 1.528-1.145C21.69 2.28 24 3.434 24 5.457z"/></svg>
        Gmail
      </a>
    </div>
  </div>

  <div class="content">

    <!-- Currently working with -->
    <div class="section">
      <div class="section-title">🛠️ I'm currently working with ...</div>
      <div class="group-label">Frontend</div>
      <div class="tech-badges">
        <span class="tech-badge" style="background:#E34F26;">
          <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg"> HTML5
        </span>
        <span class="tech-badge" style="background:#1572B6;">
          <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg"> CSS3
        </span>
        <span class="tech-badge" style="background:#20232A; border:1px solid #444;">
          <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/react/react-original.svg"> React
        </span>
        <span class="tech-badge" style="background:#c9a800; color:#fff;">
          <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg"> JavaScript
        </span>
      </div>
      <div class="group-label">Backend &amp; Tools</div>
      <div class="tech-badges">
        <span class="tech-badge" style="background:#339933;">
          <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nodejs/nodejs-original.svg"> Node.js
        </span>
        <span class="tech-badge" style="background:#303030; border:1px solid #555;">Express.js</span>
        <span class="tech-badge" style="background:#4EA94B;">
          <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mongodb/mongodb-original.svg"> MongoDB
        </span>
        <span class="tech-badge" style="background:#3a7a22;">JWT</span>
        <span class="tech-badge" style="background:#F05032;">
          <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/git/git-original.svg"> Git
        </span>
        <span class="tech-badge" style="background:#FF6C37;">Postman</span>
        <span class="tech-badge" style="background:#3aad6e;">Vercel</span>
      </div>
    </div>

    <div class="divider"></div>

    <!-- Currently learning -->
    <div class="section">
      <div class="section-title">🌱 I'm currently learning...</div>
      <div class="tech-badges">
        <span class="tech-badge" style="background:#3178C6;">
          <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/typescript/typescript-original.svg"> TypeScript
        </span>
        <span class="tech-badge" style="background:#3a7a22;">Next.js</span>
        <span class="tech-badge" style="background:#2496ED;">
          <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/docker/docker-original.svg"> Docker
        </span>
        <span class="tech-badge" style="background:#336791;">
          <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/postgresql/postgresql-original.svg"> PostgreSQL
        </span>
      </div>
    </div>

    <div class="divider"></div>

    <!-- Writing -->
    <div class="section">
      <div class="section-title">💬 Sometimes I like to write things here...</div>
      <div class="tech-badges">
        <a href="https://dev.to/" target="_blank" class="tech-badge" style="background:#0A0A0A;">Dev.to</a>
        <a href="https://medium.com/" target="_blank" class="tech-badge" style="background:#3a7a22;">Medium</a>
      </div>
    </div>

    <div class="divider"></div>

    <!-- Projects -->
    <div class="section">
      <div class="section-title">🗂️ Projects</div>
      <table class="projects-table">
        <thead>
          <tr>
            <th style="width:28%">Project</th>
            <th style="width:50%">Description</th>
            <th style="width:22%">Links</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td><div class="proj-name">🎫 Event Hub</div></td>
            <td><div class="proj-desc">JWT, refresh tokens, bcrypt, role-based access control. Production-ready authentication patterns.</div></td>
            <td>
              <div class="link-badges">
                <a href="https://github.com/gkdhass/EventHub" class="link-badge lb-repo" target="_blank">Repo</a>
              </div>
            </td>
          </tr>
          <tr>
            <td><div class="proj-name">🎵 Music Streaming</div></td>
            <td><div class="proj-desc">Playlists, search, audio player. User profiles &amp; favorites. Full MERN experience.</div></td>
            <td>
              <div class="link-badges">
                <a href="https://github.com/gkdhass/music-streaming" class="link-badge lb-repo" target="_blank">Repo</a>
                <a href="https://mohanmusic.vercel.app/" class="link-badge lb-live" target="_blank">Live</a>
              </div>
            </td>
          </tr>
          <tr>
            <td><div class="proj-name">🌐 Portfolio</div></td>
            <td><div class="proj-desc">Responsive and performant. Showcases projects and skills.</div></td>
            <td>
              <div class="link-badges">
                <a href="https://github.com/gkdhass/portfolio" class="link-badge lb-repo" target="_blank">Repo</a>
                <a href="https://mohandhass.vercel.app/" class="link-badge lb-live" target="_blank">Live</a>
              </div>
            </td>
          </tr>
        </tbody>
      </table>
      <a href="https://github.com/gkdhass?tab=repositories" class="view-all" target="_blank">👉 View all repositories →</a>
    </div>

  </div>

  <div class="wave-bottom"></div>
</div>
</body>
</html>
