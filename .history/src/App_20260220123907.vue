<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Pramod N · executive portfolio</title>
  <!-- Element Plus (full experience) & icons -->
  <link rel="stylesheet" href="https://unpkg.com/element-plus/dist/index.css" />
  <!-- Fonts & extra polish -->
  <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,500;14..32,600;14..32,700&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Inter', sans-serif;
      background: radial-gradient(circle at 10% 30%, #0f172a, #030614);
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 2rem 1.5rem;
      position: relative;
      overflow-x: hidden;
    }

    /* animated floating graphics (elements ui style) */
    .floating-bg {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      pointer-events: none;
      z-index: 0;
    }

    .float-shape {
      position: absolute;
      background: rgba(64, 158, 255, 0.03);
      border-radius: 50%;
      filter: blur(70px);
      animation: float 20s infinite alternate ease-in-out;
    }

    .shape1 {
      width: 400px; height: 400px; background: #2b5f8a; top: -100px; right: -100px; opacity: 0.25;
    }
    .shape2 {
      width: 550px; height: 550px; background: #4f8bc9; bottom: -200px; left: -150px; opacity: 0.2; animation-duration: 30s;
    }
    .shape3 {
      width: 300px; height: 300px; background: #1e3a5f; top: 40%; left: 20%; filter: blur(90px); opacity: 0.3; animation: float 25s reverse;
    }

    @keyframes float {
      0% { transform: translate(0, 0) scale(1); }
      100% { transform: translate(60px, 40px) scale(1.2); }
    }

    /* main container — different LAYOUT: 2-column glass dashboard */
    .resume-dashboard {
      max-width: 1400px;
      width: 100%;
      display: grid;
      grid-template-columns: 1.1fr 2.2fr;
      gap: 1.8rem;
      z-index: 10;
      position: relative;
      animation: revealDash 0.9s cubic-bezier(0.16, 1, 0.3, 1) forwards;
    }

    @keyframes revealDash {
      0% { opacity: 0; transform: scale(0.96) translateY(20px); }
      100% { opacity: 1; transform: scale(1) translateY(0); }
    }

    /* common glass card style */
    .glass-panel {
      background: rgba(18, 28, 46, 0.7) !important;
      backdrop-filter: blur(14px) saturate(200%);
      -webkit-backdrop-filter: blur(14px) saturate(200%);
      border: 1px solid rgba(74, 144, 226, 0.25) !important;
      border-radius: 42px !important;
      box-shadow: 0 35px 68px -20px rgba(0, 20, 40, 0.6), inset 0 0 0 1px rgba(255,255,255,0.06) !important;
      transition: all 0.4s;
      color: #eef5ff;
    }

    .glass-panel:hover {
      border-color: rgba(100, 180, 255, 0.5) !important;
      box-shadow: 0 40px 80px -15px #0b1b33, inset 0 0 20px rgba(64,158,255,0.1) !important;
    }

    /* left column — compact & powerful (profile + skills + passions) */
    .left-panel {
      display: flex;
      flex-direction: column;
      gap: 1.8rem;
    }

    .profile-card {
      padding: 2rem 1.8rem !important;
      text-align: center;
      background: rgba(12, 22, 38, 0.8) !important;
    }

    .profile-pic-frame {
      width: 140px;
      height: 140px;
      margin: 0 auto 1.2rem;
      border-radius: 50%;
      background: linear-gradient(145deg, #3167a5, #64b5f6);
      display: flex;
      align-items: center;
      justify-content: center;
      animation: borderPulse 3s infinite alternate;
      box-shadow: 0 20px 30px -8px #001a33;
    }

    @keyframes borderPulse {
      0% { box-shadow: 0 0 0 0 #409eff80, 0 20px 30px -8px #001a33; }
      100% { box-shadow: 0 0 0 8px #409eff30, 0 25px 35px -5px #0a2b50; }
    }

    .profile-pic-frame img {
      width: 130px;
      height: 130px;
      border-radius: 50%;
      object-fit: cover;
      border: 3px solid #ffffffd9;
      transition: 0.3s;
      background: #172941;
    }

    .profile-pic-frame img:hover {
      transform: scale(1.02);
      border-color: #aad0ff;
    }

    .left-panel h2 {
      font-size: 2.2rem;
      font-weight: 700;
      background: linear-gradient(120deg, #ffffff, #bddcff);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
      margin: 0.2rem 0 0.2rem;
    }

    .left-panel .title-tag {
      background: #1f3d6b;
      padding: 0.4rem 1.2rem;
      border-radius: 40px;
      display: inline-block;
      font-weight: 500;
      font-size: 1rem;
      letter-spacing: 0.3px;
      margin-bottom: 1.6rem;
      border: 1px solid #3b6bb0;
    }

    .contact-compact {
      background: #0d1b2f;
      border-radius: 36px;
      padding: 1.2rem 1rem;
      display: flex;
      flex-direction: column;
      gap: 0.8rem;
      border: 1px solid #264a78;
      margin-bottom: 1rem;
    }

    .contact-row {
      display: flex;
      align-items: center;
      gap: 0.8rem;
      font-size: 0.95rem;
      color: #c7deff;
    }

    .contact-row i {
      width: 24px;
      color: #6aa9ff;
      font-size: 1.25rem;
    }

    .contact-row a {
      color: #bbd6ff;
      text-decoration: none;
      border-bottom: 1px dashed #3f6cb0;
    }

    .skill-block {
      background: #10233e;
      border-radius: 30px;
      padding: 1.2rem;
      margin-top: 0.4rem;
    }

    .skill-block h4 {
      font-size: 1.2rem;
      margin-bottom: 0.8rem;
      border-left: 4px solid #409eff;
      padding-left: 0.8rem;
    }

    .skill-pills {
      display: flex;
      flex-wrap: wrap;
      gap: 0.5rem;
    }

    .el-tag {
      background: rgba(64, 158, 255, 0.18) !important;
      border: 1px solid #2f5585 !important;
      color: #d6e9ff !important;
      font-weight: 500;
      padding: 0.5rem 1rem !important;
      height: auto !important;
      border-radius: 30px !important;
      backdrop-filter: blur(10px);
      transition: 0.2s;
      font-size: 0.9rem;
    }

    .el-tag:hover {
      background: #2c5380 !important;
      color: white !important;
      transform: translateY(-2px);
    }

    .passion-row {
      display: flex;
      justify-content: space-around;
      margin-top: 1rem;
    }
    .passion-item {
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 0.4rem;
      background: #091c33;
      padding: 0.8rem 0.5rem;
      border-radius: 40px;
      width: 30%;
      border: 1px solid #2d5082;
    }
    .passion-item i {
      font-size: 2rem;
      color: #6aa9ff;
    }

    /* right column — multi-section timeline/grid */
    .right-panel {
      display: flex;
      flex-direction: column;
      gap: 1.8rem;
    }

    .section-card {
      padding: 1.8rem 2rem !important;
      overflow: hidden;
    }

    .section-header {
      display: flex;
      align-items: center;
      gap: 0.8rem;
      margin-bottom: 1.5rem;
    }

    .section-header i {
      font-size: 2rem;
      background: linear-gradient(145deg, #3471c9, #6fb3ff);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
    }

    .section-header h3 {
      font-size: 1.8rem;
      font-weight: 600;
      color: white;
      letter-spacing: -0.3px;
      margin: 0;
    }

    .exp-item, .edu-item, .project-item {
      position: relative;
      padding-left: 1.8rem;
      border-left: 2px solid #2e5790;
      margin-bottom: 1.8rem;
      transition: 0.2s;
    }

    .exp-item:hover, .edu-item:hover, .project-item:hover {
      border-left-color: #7bb9ff;
      transform: translateX(6px);
    }

    .exp-item::before, .edu-item::before, .project-item::before {
      content: "●";
      position: absolute;
      left: -9px;
      top: 0;
      color: #6aa9ff;
      font-size: 1.3rem;
      background: #102944;
      border-radius: 50%;
      width: 18px;
      text-align: center;
      line-height: 1;
    }

    .exp-title {
      font-size: 1.3rem;
      font-weight: 700;
      color: #cbe2ff;
    }
    .exp-sub {
      font-weight: 500;
      color: #9bb9e6;
      margin: 0.2rem 0 0.3rem;
    }
    .exp-date {
      display: inline-block;
      background: #1f3b60;
      padding: 0.2rem 1.2rem;
      border-radius: 30px;
      font-size: 0.85rem;
      font-weight: 500;
      border: 1px solid #3f6396;
      margin-bottom: 0.6rem;
    }

    .project-tech {
      display: flex;
      flex-wrap: wrap;
      gap: 0.5rem;
      margin: 0.8rem 0 0.2rem;
    }

    .project-tech span {
      background: #102847;
      border-radius: 30px;
      padding: 0.2rem 1rem;
      font-size: 0.8rem;
      border: 1px solid #2b5282;
    }

    /* summary highlight */
    .summary-glass {
      background: rgba(20, 40, 68, 0.8);
      border-radius: 32px;
      padding: 1.6rem;
      line-height: 1.7;
      border: 1px solid #2a5580;
      backdrop-filter: blur(8px);
    }

    /* Element UI carousel / graphics (simulated with pure css) */
    .graphic-divider {
      display: flex;
      align-items: center;
      gap: 1rem;
      margin: 1rem 0;
    }
    .graphic-line {
      height: 2px;
      flex: 1;
      background: linear-gradient(90deg, transparent, #409eff, #a0c8ff, transparent);
    }
    .graphic-icon i {
      color: #5893df;
      font-size: 1.4rem;
      opacity: 0.9;
    }

    /* timeline animation on view */
    @keyframes slideInRight {
      from { opacity: 0; transform: translateX(25px); }
      to { opacity: 1; transform: translateX(0); }
    }

    .right-panel .section-card {
      animation: slideInRight 0.5s both;
    }
    .right-panel .section-card:nth-child(1) { animation-delay: 0.1s; }
    .right-panel .section-card:nth-child(2) { animation-delay: 0.2s; }
    .right-panel .section-card:nth-child(3) { animation-delay: 0.3s; }
    .right-panel .section-card:nth-child(4) { animation-delay: 0.4s; }

    /* modern scroll */
    ::-webkit-scrollbar { width: 6px; }
    ::-webkit-scrollbar-track { background: #04152b; border-radius: 20px; }
    ::-webkit-scrollbar-thumb { background: #1f4980; border-radius: 20px; }

    /* additional element ui style stats */
    .stat-badge {
      background: #133053;
      border-radius: 40px;
      padding: 0.5rem 1.2rem;
      display: inline-flex;
      align-items: center;
      gap: 0.5rem;
      border: 1px solid #3865a3;
      font-weight: 500;
    }

    /* responsive */
    @media (max-width: 1000px) {
      .resume-dashboard { grid-template-columns: 1fr; }
    }
  </style>
</head>
<body>
  <!-- floating graphics (atmospheric) -->
  <div class="floating-bg">
    <div class="float-shape shape1"></div>
    <div class="float-shape shape2"></div>
    <div class="float-shape shape3"></div>
  </div>

  <!-- main dashboard: two column advanced layout -->
  <div class="resume-dashboard">
    <!-- LEFT PANEL: profile, compact contact, skills, passions  -->
    <div class="left-panel">
      <el-card shadow="hover" class="glass-panel profile-card">
        <div class="profile-pic-frame">
          <img src="./1000005132.jpg" alt="Pramod N" onerror="this.onerror=null; this.src='data:image/svg+xml,%3Csvg%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20width%3D%22130%22%20height%3D%22130%22%20viewBox%3D%220%200%20100%20100%22%3E%3Ccircle%20cx%3D%2250%22%20cy%3D%2250%22%20r%3D%2245%22%20fill%3D%22%233b6cb0%22%20/%3E%3Ctext%20x%3D%2250%22%20y%3D%2268%22%20font-size%3D%2238%22%20text-anchor%3D%22middle%22%20fill%3D%22%23ffffff%22%20dy%3D%22.3em%22%3EPN%3C%2Ftext%3E%3C%2Fsvg%3E' );">
        </div>
        <h2>PRAMOD N</h2>
        <span class="title-tag">MCA · Asst. Professor · Researcher</span>

        <div class="contact-compact">
          <div class="contact-row"><i class="fas fa-phone-alt"></i> +91 8861326592</div>
          <div class="contact-row"><i class="fas fa-envelope"></i> pramod.n1301@gmail.com</div>
          <div class="contact-row"><i class="fab fa-linkedin"></i> <a href="https://linkedin.com/in/pramod-n-a965b9264/" target="_blank">/in/pramod-n</a></div>
          <div class="contact-row"><i class="fas fa-map-marker-alt"></i> Bangalore, KA</div>
        </div>

        <!-- SKILLS compact as element tags -->
        <div class="skill-block">
          <h4><i class="fas fa-code" style="margin-right: 8px;"></i> tech toolkit</h4>
          <div class="skill-pills">
            <el-tag size="large" effect="dark">Java</el-tag>
            <el-tag size="large" effect="dark">Python</el-tag>
            <el-tag size="large" effect="dark">JavaScript</el-tag>
            <el-tag size="large" effect="dark">Node.js</el-tag>
            <el-tag size="large" effect="dark">Express</el-tag>
            <el-tag size="large" effect="dark">Firebase</el-tag>
            <el-tag size="large" effect="dark">SQL</el-tag>
            <el-tag size="large" effect="dark">Android</el-tag>
            <el-tag size="large" effect="dark">OpenCV</el-tag>
            <el-tag size="large" effect="dark">Figma</el-tag>
            <el-tag size="large" effect="dark">AWS Lambda</el-tag>
            <el-tag size="large" effect="dark">Git</el-tag>
            <el-tag size="large" effect="dark">Postman</el-tag>
            <el-tag size="large" effect="dark">WebRTC</el-tag>
          </div>
        </div>

        <!-- languages + passions with graphics -->
        <div style="margin-top: 1.2rem;">
          <div class="stat-badge"><i class="fas fa-language"></i> Kannada (native) · Hindi · English</div>
        </div>
        <div class="passion-row">
          <div class="passion-item"><i class="fas fa-plane"></i><span>Travel</span></div>
          <div class="passion-item"><i class="fas fa-swimmer"></i><span>Swim</span></div>
          <div class="passion-item"><i class="fas fa-camera"></i><span>Photo</span></div>
        </div>
      </el-card>
    </div>

    <!-- RIGHT PANEL: summary, experience, education, projects (multi-format) -->
    <div class="right-panel">
      <!-- SUMMARY card with animation & graphic -->
      <el-card shadow="hover" class="glass-panel section-card">
        <div class="section-header">
          <i class="fas fa-user-astronaut"></i>
          <h3>profile</h3>
        </div>
        <div class="summary-glass">
          <p style="font-size: 1.05rem;">Motivated academic and developer with experience as Assistant Professor, strong foundation in computer applications, passionate about teaching, research & innovative projects. Eager to leverage technical, academic, and research skills in dynamic environments.</p>
        </div>
        <div class="graphic-divider">
          <span class="graphic-line"></span>
          <span class="graphic-icon"><i class="fas fa-bolt"></i></span>
          <span class="graphic-line"></span>
        </div>
        <div style="display: flex; gap: 1rem; justify-content: flex-end;">
          <el-tag size="small" effect="plain" style="background: transparent;">Ph.D. (ongoing)</el-tag>
          <el-tag size="small" effect="plain" style="background: transparent;">IoT · Blockchain</el-tag>
        </div>
      </el-card>

      <!-- EXPERIENCE card with timeline elements -->
      <el-card shadow="hover" class="glass-panel section-card">
        <div class="section-header">
          <i class="fas fa-briefcase"></i>
          <h3>experience</h3>
        </div>
        <div class="exp-item">
          <div class="exp-title">Assistant Professor</div>
          <div class="exp-sub">Dept of MCA, Nitte Meenakshi Institute of Technology</div>
          <span class="exp-date"><i class="far fa-calendar-alt" style="margin-right: 6px;"></i>Aug 2024 – Jul 2025</span>
          <ul style="margin-top: 10px; padding-left: 1.2rem; color: #c9dcff;">
            <li style="margin-bottom: 6px;">Taught MCA core: programming, data structures, project dev.</li>
            <li style="margin-bottom: 6px;">Mentored postgraduate research projects & coordinated workshops.</li>
            <li>Curriculum planning & departmental accreditation.</li>
          </ul>
        </div>
        <!-- more experience can be added, but just one, looks clean -->
      </el-card>

      <!-- EDUCATION card with modern grid feel -->
      <el-card shadow="hover" class="glass-panel section-card">
        <div class="section-header">
          <i class="fas fa-graduation-cap"></i>
          <h3>education</h3>
        </div>
        <div style="display: flex; flex-direction: column; gap: 1rem;">
          <div class="edu-item">
            <b>Ph.D. (Computer Science)</b> – started 2025<br>
            <span style="color: #b0ceff;">Nitte Meenakshi Institute of Technology (Research centre)</span><br>
            <span style="background: #173257; padding: 0.2rem 0.8rem; border-radius: 30px; font-size: 0.85rem;">IoT + Blockchain</span>
          </div>
          <div class="edu-item">
            <b>MCA</b> | CGPA 7.4/10 · 2022–2024<br>
            <span style="color: #b0ceff;">BMS Institute of Technology, Bengaluru</span>
          </div>
          <div class="edu-item">
            <b>B.Sc</b> | CGPA 7.4/10 · 2019–2022<br>
            <span style="color: #b0ceff;">MES Degree College, Bengaluru</span>
          </div>
          <div style="display: flex; gap: 1rem; flex-wrap: wrap;">
            <div class="stat-badge"><i class="fas fa-school"></i> PUC: 65%</div>
            <div class="stat-badge"><i class="fas fa-medal"></i> SSLC: 87%</div>
          </div>
        </div>
      </el-card>

      <!-- PROJECTS card: interactive chips and descriptions -->
      <el-card shadow="hover" class="glass-panel section-card">
        <div class="section-header">
          <i class="fas fa-flask"></i>
          <h3>research & projects</h3>
        </div>
        <div class="project-item">
          <b style="font-size: 1.1rem;">Smart Doctor</b> 
          <el-tag size="small" style="margin-left: 10px; background: #264a78;">KSCST shortlisted</el-tag>
          <div class="project-tech"><span>Java</span><span>Android</span><span>Firebase</span><span>SQL</span></div>
          <p style="color: #c3d9ff;">Healthcare mobile app: smart diagnosis & doctor consultation.</p>
        </div>
        <div class="project-item">
          <b>Driver Drowsiness Alert</b>
          <div class="project-tech"><span>Python</span><span>OpenCV</span><span>ML</span></div>
          <p style="color: #c3d9ff;">Real-time computer vision fatigue detection.</p>
        </div>
        <div class="project-item">
          <b>Video Conference App</b>
          <div class="project-tech"><span>Node.js</span><span>Express</span><span>WebRTC</span><span>Firebase</span></div>
          <p style="color: #c3d9ff;">Cross-platform video conferencing with chat & auth (Render).</p>
        </div>
        <div class="project-item">
          <b>AQI Analysis App</b>
          <div class="project-tech"><span>Python</span><span>REST API</span><span>Android</span></div>
          <p style="color: #c3d9ff;">Fetches & visualizes Air Quality Index.</p>
        </div>
        <div class="project-item">
          <b>E-Library Management</b>
          <div class="project-tech"><span>Node.js</span><span>Express</span><span>SQL</span><span>Firebase</span></div>
          <p style="color: #c3d9ff;">Full-stack digital library with admin/student access.</p>
        </div>

        <!-- animated element ui carousel substitute (graphic) -->
        <div class="graphic-divider">
          <span class="graphic-line"></span>
          <span class="graphic-icon"><i class="fas fa-crown" style="color: #ffd966;"></i></span>
          <span class="graphic-line"></span>
        </div>
        <div style="display: flex; gap: 0.8rem; justify-content: center;">
          <i class="fas fa-database" style="color: #6ea8ff;"></i>
          <i class="fas fa-cloud" style="color: #6ea8ff;"></i>
          <i class="fas fa-laptop-code" style="color: #6ea8ff;"></i>
        </div>
      </el-card>
    </div>
  </div>

  <!-- load element plus and vue (optional but just for structure) -->
  <script src="https://unpkg.com/vue@3/dist/vue.global.js"></script>
  <script src="https://unpkg.com/element-plus"></script>
  <script>
    // minimal Vue instance to enable Element components (tags already rendered as html)
    // but we need to mount for dynamic? just static fine.
  </script>
  <script>
    // extra smoothness for tag hover etc
  </script>
</body>
</html>