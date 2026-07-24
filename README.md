<!-- 
  ===========================================================
  🌌 100% GITHUB-PROOF WALLPAPER ENGINE (LIGHT GREEN THEME)
  ===========================================================
  No backdrop-filter. Pure rgba + animations.
  Renders perfectly on GitHub profile views.
-->

<style>
  /* ===========================================================
     🌈 LIGHT GREEN / NEON MINT THEME (ACTIVE)
     =========================================================== */
  
  :root {
    --orb-1: #39ff14;
    --orb-2: #00ff88;
    --orb-3: #55efc4;
    --text-accent: #7bed9f;
    --card-bg: rgba(10, 25, 15, 0.88);
    --border-glow: #39ff14;
    --shadow-color: rgba(57, 255, 20, 0.3);
    --text-primary: #d4fad4;
    --grid-color: rgba(57, 255, 20, 0.08);
  }
  /*
  --- THEME 2: OCEAN CYBER (Blue) --- 
  :root {
    --orb-1: #00d4ff;
    --orb-2: #090979;
    --orb-3: #1a0b2e;
    --text-accent: #00d4ff;
    --card-bg: rgba(10, 14, 23, 0.88);
    --border-glow: #00d4ff;
    --shadow-color: rgba(0, 212, 255, 0.3);
    --text-primary: #e6f1ff;
    --grid-color: rgba(0, 212, 255, 0.06);
  }
  */

  /* ===========================================================
     🖥️ THE MAIN WRAPPER
     =========================================================== */
  
  .profile-wrapper {
    position: relative;
    overflow: hidden;
    border-radius: 32px;
    padding: 20px;
    background: #050a06; /* Deep green-black base */
    box-shadow: 0 20px 60px rgba(0, 0, 0, 0.9);
    border: 1px solid rgba(57, 255, 20, 0.15);
    font-family: 'Segoe UI', 'Poppins', system-ui, sans-serif;
    color: var(--text-primary);
  }

  /* ===========================================================
     🌊 LIQUID BACKGROUND
     =========================================================== */
  
  .bg-layer {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: 0;
    background: 
      radial-gradient(circle at 20% 30%, var(--orb-1), transparent 50%),
      radial-gradient(circle at 80% 70%, var(--orb-2), transparent 55%),
      radial-gradient(circle at 40% 90%, var(--orb-3), transparent 45%);
    background-blend-mode: screen;
    animation: liquidMove 22s infinite alternate ease-in-out;
  }

  @keyframes liquidMove {
    0%   { background-position: 0% 0%, 50% 50%, 100% 100%; background-size: 100% 100%, 80% 80%, 60% 60%; }
    33%  { background-position: 20% 30%, 70% 20%, 40% 80%; background-size: 120% 120%, 90% 90%, 70% 70%; }
    66%  { background-position: 80% 10%, 20% 80%, 90% 30%; background-size: 90% 90%, 110% 110%, 80% 80%; }
    100% { background-position: 40% 70%, 90% 60%, 10% 20%; background-size: 110% 110%, 70% 70%, 100% 100%; }
  }

  /* ===========================================================
     🟣 FLOATING ORBS
     =========================================================== */
  
  .orb {
    position: absolute;
    border-radius: 50%;
    filter: blur(100px);
    opacity: 0.35;
    z-index: 0;
    pointer-events: none;
    animation: floatOrb 20s infinite alternate ease-in-out;
  }
  .orb-1 { width: 400px; height: 400px; background: var(--orb-1); top: -150px; left: -100px; animation-duration: 22s; }
  .orb-2 { width: 500px; height: 500px; background: var(--orb-2); bottom: -180px; right: -120px; animation-duration: 26s; animation-delay: -5s; }
  .orb-3 { width: 300px; height: 300px; background: var(--orb-3); top: 30%; left: 30%; animation-duration: 30s; animation-delay: -10s; }

  @keyframes floatOrb {
    0%   { transform: translate(0px, 0px) scale(1); }
    50%  { transform: translate(40px, -60px) scale(1.2); }
    100% { transform: translate(-40px, 50px) scale(0.9); }
  }

  /* ===========================================================
     📡 CYBER GRID OVERLAY
     =========================================================== */
  
  .grid-overlay {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: 0;
    background-image: 
      linear-gradient(var(--grid-color) 1px, transparent 1px),
      linear-gradient(90deg, var(--grid-color) 1px, transparent 1px);
    background-size: 50px 50px;
    animation: gridScroll 30s linear infinite;
    pointer-events: none;
    mask-image: radial-gradient(ellipse at center, black 20%, transparent 75%);
    -webkit-mask-image: radial-gradient(ellipse at center, black 20%, transparent 75%);
  }

  @keyframes gridScroll {
    0%   { transform: perspective(400px) rotateX(1.5deg) translateY(0px); }
    100% { transform: perspective(400px) rotateX(1.5deg) translateY(50px); }
  }

  /* ===========================================================
     💎 CONTENT (No backdrop-filter, uses solid rgba)
     =========================================================== */
  
  .content {
    position: relative;
    z-index: 1;
  }

  .glow-card {
    background: var(--card-bg);
    border: 1px solid rgba(57, 255, 20, 0.1);
    border-radius: 24px;
    padding: 24px;
    margin-bottom: 24px;
    box-shadow: 0 8px 32px rgba(0, 0, 0, 0.5);
    transition: transform 0.3s ease, border-color 0.3s ease, box-shadow 0.3s ease;
    border-left: 4px solid var(--border-glow);
  }
  .glow-card:hover {
    transform: translateY(-4px);
    border-color: var(--border-glow);
    box-shadow: 0 12px 48px var(--shadow-color);
  }

  .split-grid {
    display: grid;
    grid-template-columns: 1fr 1.5fr;
    gap: 24px;
  }
  @media (max-width: 700px) {
    .split-grid { grid-template-columns: 1fr; }
  }

  .glitch-text {
    font-size: 2.6em;
    font-weight: 800;
    background: linear-gradient(45deg, var(--orb-1), var(--orb-2));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    display: inline-block;
    animation: glitchPulse 3s infinite;
  }
  @keyframes glitchPulse {
    0%, 100% { filter: drop-shadow(0 0 15px var(--orb-1)); }
    50% { filter: drop-shadow(0 0 40px var(--orb-2)); }
  }

  .section-title {
    font-size: 1.6em;
    font-weight: 700;
    margin-bottom: 18px;
    color: var(--text-primary);
    border-left: 6px solid var(--border-glow);
    padding-left: 15px;
  }

  .flex-badges {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    justify-content: center;
  }

  /* Fix for images inside cards */
  .glow-card img {
    max-width: 100%;
    border-radius: 8px;
  }
</style>

<!-- =========================================================== -->
<!--  🚀 PROFILE WRAPPER                                          -->
<!-- =========================================================== -->

<div class="profile-wrapper">

  <!-- Background Layers -->
  <div class="bg-layer"></div>
  <div class="orb orb-1"></div>
  <div class="orb orb-2"></div>
  <div class="orb orb-3"></div>
  <div class="grid-overlay"></div>

  <!-- Content -->
  <div class="content">

    <!-- ============ HERO ============ -->
    <div class="split-grid">
      <div class="glow-card" style="display: flex; flex-direction: column; justify-content: center; align-items: center; text-align: center;">
        <div style="font-size: 4em; filter: drop-shadow(0 0 30px var(--orb-1));">⚡</div>
        <h1 style="margin: 0;"><span class="glitch-text">M.F Umair</span></h1>
        <p style="font-size: 1.1em; letter-spacing: 2px; color: var(--text-accent); font-weight: 600;">FULL-STACK ARCHITECT</p>
        <div style="display: flex; gap: 8px; flex-wrap: wrap; justify-content: center; margin-top: 8px;">
          <img src="https://komarev.com/ghpvc/?username=mohemedumair10680-sketch&label=🌍+VISITORS&color=39ff14&style=flat-square" />
          <img src="https://img.shields.io/badge/Status-Coding_24/7-39ff14?style=flat-square&logo=statuspage&color=050a06" />
        </div>
      </div>
      <div class="glow-card" style="display: flex; flex-direction: column; justify-content: center;">
        <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=24&duration=2800&pause=1000&color=39FF14&center=false&vCenter=true&width=500&lines=Backend+%26+Cloud+Enthusiast;REST+API+Master;React+%2B+Node+Stack;Docker+%7C+AWS+%7C+Linux;Always+Building+%F0%9F%9A%80" alt="Typing" style="max-width:100%;" />
        <div style="margin-top: 16px; display: flex; flex-wrap: wrap; gap: 16px;">
          <span>📍 <strong>Earth</strong> 🌍</span>
          <span>📚 <strong>Learning:</strong> React Native & Go</span>
          <span>☕ <strong>Fuel:</strong> Espresso</span>
        </div>
      </div>
    </div>

    <!-- ============ TECH STACK ============ -->
    <div class="glow-card">
      <h2 class="section-title">🛠️ The Armory</h2>
      <div class="flex-badges">
        <img src="https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=39FF14" />
        <img src="https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=39FF14" />
        <img src="https://img.shields.io/badge/Express.js-000000?style=for-the-badge&logo=express&logoColor=39FF14" />
        <img src="https://img.shields.io/badge/MySQL-005C84?style=for-the-badge&logo=mysql&logoColor=39FF14" />
        <img src="https://img.shields.io/badge/MongoDB-4EA94B?style=for-the-badge&logo=mongodb&logoColor=39FF14" />
        <img src="https://img.shields.io/badge/Docker-2CA5E0?style=for-the-badge&logo=docker&logoColor=39FF14" />
        <img src="https://img.shields.io/badge/AWS-232F3E?style=for-the-badge&logo=amazon-aws&logoColor=39FF14" />
        <img src="https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=github-actions&logoColor=39FF14" />
        <img src="https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=39FF14" />
      </div>
    </div>

    <!-- ============ STATS & STREAK ============ -->
    <div class="split-grid">
      <div class="glow-card" style="display: flex; justify-content: center; align-items: center; flex-direction: column;">
        <h3 style="color: var(--text-accent); margin-top: 0;">📈 Performance</h3>
        <img src="https://github-readme-stats.vercel.app/api?username=mohemedumair10680-sketch&show_icons=true&theme=dark&hide_border=true&bg_color=0a190f&icon_color=39ff14&title_color=39ff14&text_color=7bed9f" width="100%" />
      </div>
      <div class="glow-card" style="display: flex; justify-content: center; align-items: center; flex-direction: column;">
        <h3 style="color: var(--text-accent); margin-top: 0;">🔥 Daily Streak</h3>
        <img src="https://streak-stats.demolab.com?user=mohemedumair10680-sketch&theme=dark&hide_border=true&background=0a190f&fire=39ff14&ring=39ff14&currStreakLabel=39ff14&sideLabels=7bed9f&currStreakNum=ffffff" width="100%" />
      </div>
    </div>

    <!-- ============ ACTIVITY GRAPH ============ -->
    <div class="glow-card">
      <h2 class="section-title">📈 Activity Graph</h2>
      <img src="https://github-readme-activity-graph.vercel.app/graph?username=mohemedumair10680-sketch&theme=github-dark&hide_border=true&bg_color=0a190f&color=39ff14&line=00ff88&point=39ff14" width="100%" />
    </div>

    <!-- ============ SNAKE & TROPHIES ============ -->
    <div class="glow-card">
      <h2 class="section-title">🐍 Snake & Trophies</h2>
      <div align="center">
        <picture>
          <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/mohemedumair10680-sketch/mohemedumair10680-sketch/output/snake.svg" />
          <img alt="Snake" src="https://raw.githubusercontent.com/mohemedumair10680-sketch/mohemedumair10680-sketch/output/snake.svg" width="100%" />
        </picture>
        <br><br>
        <img src="https://github-profile-trophy.vercel.app/?username=mohemedumair10680-sketch&theme=onedark&no-frame=true&row=1&column=7&margin-w=10" width="100%" />
      </div>
    </div>

    <!-- ============ FLAGSHIP PROJECT ============ -->
    <div class="glow-card">
      <h2 class="section-title">🚀 Flagship: CityFix</h2>
      <div style="display: flex; flex-wrap: wrap; gap: 20px; align-items: center;">
        <div style="background: rgba(0,0,0,0.4); padding: 18px; border-radius: 16px; flex: 1; min-width: 180px; border-left: 4px solid var(--orb-1);">
          <h3 style="margin: 0; color: var(--text-accent);">🏙️ Smart Civic Reporting</h3>
          <p style="opacity: 0.8; margin: 8px 0;">JWT Auth · RBAC · REST API · MySQL</p>
          <a href="#" style="color: var(--text-accent); text-decoration: none; border: 1px solid var(--text-accent); padding: 6px 18px; border-radius: 50px; display: inline-block; margin-top: 8px;">🔗 View Repo</a>
        </div>
        <div style="font-size: 3em; margin: 0 auto;">📱</div>
      </div>
    </div>

    <!-- ============ SPOTIFY & WAKATIME ============ -->
    <div class="split-grid">
      <div class="glow-card" style="display: flex; flex-direction: column; align-items: center;">
        <h3 class="section-title" style="font-size: 1.2em;">🎵 Vibing to</h3>
        <!-- REPLACE YOUR_SPOTIFY_UID -->
        <img src="https://spotify-github-profile.vercel.app/api/view?uid=YOUR_SPOTIFY_UID&cover_image=true&theme=compact&bar_color=39ff14&bar_color_cover=true" width="100%" />
      </div>
      <div class="glow-card" style="display: flex; flex-direction: column; align-items: center;">
        <h3 class="section-title" style="font-size: 1.2em;">⌨️ Coding Stats</h3>
        <!-- REPLACE YOUR_WAKATIME_USERNAME -->
        <img src="https://github-readme-stats.vercel.app/api/wakatime?username=YOUR_WAKATIME_USERNAME&layout=compact&theme=dark&hide_border=true&bg_color=0a190f&title_color=39ff14&text_color=7bed9f" width="100%" />
      </div>
    </div>

    <!-- ============ HOLOPIN & SOCIALS ============ -->
    <div class="glow-card" style="text-align: center;">
      <h2 class="section-title" style="text-align: center; border-left: none;">🏅 Community Badges</h2>
      <a href="https://holopin.io/@mohemedumair10680-sketch">
        <img src="https://holopin.me/mohemedumair10680-sketch" alt="Holopin" width="600" style="max-width:100%; border-radius: 16px;" />
      </a>
      <br><br>
      <div class="flex-badges">
        <a href="https://leetcode.com/YOUR_LEETCODE/"><img src="https://img.shields.io/badge/LeetCode-000000?style=for-the-badge&logo=LeetCode&logoColor=39ff14" /></a>
        <a href="https://www.hackerrank.com/YOUR_HR"><img src="https://img.shields.io/badge/-HackerRank-2EC866?style=for-the-badge&logo=HackerRank&logoColor=39ff14" /></a>
        <a href="mailto:mohemedumair10680@gmail.com"><img src="https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=39ff14" /></a>
        <a href="#"><img src="https://img.shields.io/badge/Portfolio-255E63?style=for-the-badge&logo=About.me&logoColor=39ff14" /></a>
        <a href="#"><img src="https://img.shields.io/badge/Buy_Me_A_Coffee-FFDD00?style=for-the-badge&logo=buy-me-a-coffee&logoColor=050a06" /></a>
      </div>
      <hr style="border-color: var(--border-glow); opacity: 0.2; margin: 25px 0;">
      <div style="opacity: 0.7; font-size: 0.9rem;">
        ⭐ <strong>“Clean code, continuous learning, and consistency build the future.”</strong> ⭐
      </div>
    </div>

  </div> <!-- End content -->
</div> <!-- End profile-wrapper -->
