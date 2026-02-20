<template>
  <div class="resume-wrapper">
    <el-card shadow="hover" class="resume-card">
      <!-- header with animation & image (works even without actual 1000005132.jpg, will show alt/ broken icon, but fine) -->
      <div class="header">
        <img class="profile-pic" src="./1000005132.jpg" alt="Pramod N" onerror="this.onerror=null; this.src='data:image/svg+xml,%3Csvg%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20width%3D%22130%22%20height%3D%22130%22%20viewBox%3D%220%200%20100%20100%22%3E%3Ccircle%20cx%3D%2250%22%20cy%3D%2250%22%20r%3D%2245%22%20fill%3D%22%23409eff%22%20%2F%3E%3Ctext%20x%3D%2250%22%20y%3D%2268%22%20font-size%3D%2238%22%20text-anchor%3D%22middle%22%20fill%3D%22white%22%20dy%3D%22.3em%22%3EPN%3C%2Ftext%3E%3C%2Fsvg%3E' ;">
        <div class="contact-info">
          <h2>PRAMOD N</h2>
          <p>
            <el-icon><i class="el-icon-phone" style="font-weight: bold;"></i></el-icon> +91 8861326592 &nbsp;|&nbsp;
            <el-icon><i class="el-icon-message"></i></el-icon> pramod.n1301@gmail.com &nbsp;|&nbsp;
            <el-icon><i class="el-icon-link"></i></el-icon>
            <a href="https://linkedin.com/in/pramod-n-a965b9264/" target="_blank">linkedin.com/in/pramod-n</a> &nbsp;|&nbsp;
            <el-icon><i class="el-icon-location"></i></el-icon> Bangalore, KA
          </p>
        </div>
      </div>

      <el-divider></el-divider>

      <!-- SUMMARY with animation -->
      <section>
        <h3>SUMMARY</h3>
        <p style="background: #f6faff; border-radius: 30px; padding: 1.2rem 1.8rem; font-size: 1.05rem; line-height: 1.6; box-shadow: inset 0 2px 6px #ffffff, 0 10px 15px -18px #163458;">
          Motivated and detail-oriented academic and developer with experience as an Assistant Professor and a strong foundation in computer applications. Passionate about teaching, research, and contributing to innovative projects. Eager to leverage technical, academic, and research skills in dynamic environments.
        </p>
      </section>

      <el-divider></el-divider>

      <!-- SKILLS with modern chip layout -->
      <section>
        <h3>SKILLS</h3>
        <ul class="skills-list">
          <li><b>Programming:</b> Java, C, Python, SQL, JavaScript</li>
          <li><b>Web & App:</b> Full Stack, Node.js, Express.js, Android, WebRTC</li>
          <li><b>Databases & Cloud:</b> Firebase, AWS Lambda, SQL</li>
          <li><b>Hosting & Deployment:</b> Vercel, Render, Netlify</li>
          <li><b>Testing & Tools:</b> Postman, cURL, Selenium</li>
          <li><b>UI/UX Design:</b> Figma, Photoshop, Premiere Pro</li>
          <li><b>Other:</b> HTML, Git & GitHub, OpenCV</li>
        </ul>
      </section>

      <el-divider></el-divider>

      <!-- EXPERIENCE enhanced -->
      <section>
        <h3>EXPERIENCE</h3>
        <div style="margin-left: 0.5rem;">
          <b style="font-size: 1.2rem;">Assistant Professor</b><br>
          <span style="font-weight: 500;">Dept of MCA, Nitte Meenakshi Institute of Technology, Bengaluru</span><br>
          <i>August 2024 – July 2025</i>
          <ul style="margin-top: 0.6rem;">
            <li>Taught core MCA subjects including programming, data structures, and project development.</li>
            <li>Mentored postgraduate students on research-oriented academic projects.</li>
            <li>Participated in academic reviews, curriculum planning, and accreditation work.</li>
            <li>Coordinated technical workshops and departmental hackathons.</li>
          </ul>
        </div>
      </section>

      <el-divider></el-divider>

      <!-- EDUCATION with visual hierarchy -->
      <section>
        <h3>EDUCATION</h3>
        <ul style="flex-direction: column; align-items: stretch; gap: 0.6rem;">
          <li><b>Ph.D. (Computer Science)</b> – started 2025<br>Nitte Meenakshi Institute of Technology (Research centre)<br><span style="color:#2a4e8a;">IoT with Blockchain</span></li>
          <li><b>MCA (Master of Computer Applications)</b> | CGPA 7.4/10<br>BMS Institute of Technology, Bengaluru (2022–2024)</li>
          <li><b>Bachelor of Science</b> | CGPA 7.4/10<br>MES Degree College, Bengaluru (2019–2022)</li>
          <li><b>PUC (12th)</b> | 65%<br>St. Claret PU College, Bengaluru (2017–2019)</li>
          <li><b>SSLC (10th)</b> | 87%<br>Ideal English High School, Bengaluru (2004–2017)</li>
        </ul>
      </section>

      <el-divider></el-divider>

      <!-- PROJECTS section enriched with tech tags -->
      <section>
        <h3>PROJECTS</h3>
        <ul style="flex-direction: column;">
          <li>
            <b>Smart Doctor</b> – <span style="background: #e5f0ff; border-radius: 30px; padding: 0.2rem 1rem;">KSCST shortlisted</span><br>
            <i>Tech:</i> Java, Android Studio, Firebase, SQL<br>
            Healthcare mobile app with smart diagnosis and doctor consultation.
          </li>
          <li>
            <b>Driver Drowsiness Alert System</b><br>
            <i>Tech:</i> Python, OpenCV, Machine Learning<br>
            Real-time computer vision fatigue detection.
          </li>
          <li>
            <b>Video Conference Mobile App</b><br>
            <i>Tech:</i> Node.js, Express.js, Firebase, WebRTC, Render<br>
            Cross-platform video conferencing with chat & auth.
          </li>
          <li>
            <b>Air Quality Index (AQI) Analysis App</b><br>
            <i>Tech:</i> Python, Firebase, REST APIs, Android<br>
            Fetches AQI data, interactive dashboard.
          </li>
          <li>
            <b>E-Library Management System</b><br>
            <i>Tech:</i> Full stack: Node.js, Express, Firebase, SQL<br>
            Digital library with admin and student access.
          </li>
        </ul>
      </section>

      <el-divider></el-divider>

      <!-- LANGUAGES & PASSIONS combine with style -->
      <section>
        <h3>LANGUAGES</h3>
        <p>🇮🇳 Kannada: Native  |  Hindi: Proficient  |  English: Proficient</p>
      </section>

      <el-divider></el-divider>

      <section>
        <h3>PASSIONS & INTERESTS</h3>
        <p>✈️ Travelling  ·  🏊 Swimming  ·  📸 Photography</p>
      </section>
    </el-card>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Inter:opsz@14..32&display=swap');
...existing code...
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Inter', system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
      background: linear-gradient(145deg, #eef2f8 0%, #d9e2ef 100%);
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 2rem 1rem;
      animation: fadeIn 0.8s cubic-bezier(0.2, 0.9, 0.3, 1) forwards;
    }

    @keyframes fadeIn {
      0% { opacity: 0; backdrop-filter: blur(4px); }
      100% { opacity: 1; backdrop-filter: blur(0); }
    }

    .resume-wrapper {
      max-width: 1000px;
      width: 100%;
      margin: 0 auto;
      transition: transform 0.25s ease;
    }

    /* modern card with glassmorphism lift */
    .resume-card {
      background: rgba(255, 255, 255, 0.85) !important;
      backdrop-filter: blur(12px) saturate(180%);
      -webkit-backdrop-filter: blur(12px) saturate(180%);
      border: 1px solid rgba(255, 255, 255, 0.5) !important;
      border-radius: 36px !important;
      box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.25), inset 0 1px 2px rgba(255,255,255,0.6) !important;
      padding: 2.2rem 2.2rem !important;
      transition: all 0.4s ease;
    }

    .resume-card:hover {
      box-shadow: 0 35px 60px -15px rgba(28, 52, 84, 0.4), 0 0 0 1px rgba(255,255,255,0.8) inset !important;
      transform: scale(1.008);
      background: rgba(255, 255, 255, 0.92) !important;
    }

    /* animated header with profile pic */
    .header {
      display: flex;
      flex-wrap: wrap;
      align-items: center;
      gap: 2rem;
      margin-bottom: 1.8rem;
      animation: slideUp 0.5s 0.1s both;
    }

    @keyframes slideUp {
      from { opacity: 0; transform: translateY(18px); }
      to { opacity: 1; transform: translateY(0); }
    }

    .profile-pic {
      width: 130px;
      height: 130px;
      object-fit: cover;
      border-radius: 50%;
      border: 4px solid #ffffffd9;
      box-shadow: 0 20px 30px -10px rgba(34, 67, 117, 0.4), 0 0 0 2px rgba(64,158,255,0.3);
      transition: all 0.4s ease;
      filter: brightness(1.02) contrast(1.02);
    }

    .profile-pic:hover {
      transform: scale(1.03) rotate(1deg);
      border-color: #79bbff;
      box-shadow: 0 30px 40px -12px #1f3d6b;
    }

    .contact-info h2 {
      font-size: 2.8rem;
      font-weight: 700;
      background: linear-gradient(135deg, #1e293b, #2c3e6d);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
      letter-spacing: -0.02em;
      margin: 0 0 0.4rem 0;
      line-height: 1.2;
      border-left: 6px solid #409eff;
      padding-left: 1.2rem;
    }

    .contact-info p {
      display: flex;
      flex-wrap: wrap;
      align-items: center;
      gap: 0.4rem 1rem;
      font-size: 1.05rem;
      color: #1e2f4a;
      background: rgba(255,255,255,0.5);
      padding: 0.8rem 1.4rem;
      border-radius: 60px;
      backdrop-filter: blur(4px);
      margin-top: 0.5rem;
      box-shadow: 0 4px 10px rgba(0,20,40,0.08);
    }

    .contact-info p i, .contact-info p .el-icon {
      color: #2a5fa3;
      font-size: 1.3rem;
      vertical-align: middle;
    }

    .contact-info a {
      color: #1f3f75;
      font-weight: 600;
      text-decoration: none;
      border-bottom: 1px dashed #79bbff;
      transition: all 0.2s;
    }

    .contact-info a:hover {
      color: #0a2b5a;
      border-bottom: 2px solid #409eff;
    }

    /* divider with animation */
    .el-divider {
      margin: 1.8rem 0 !important;
      border-top: 2px solid rgba(64, 158, 255, 0.2) !important;
      position: relative;
      overflow: visible;
    }
    .el-divider::after {
      content: "✦";
      position: absolute;
      left: 50%;
      top: 50%;
      transform: translate(-50%, -70%);
      background: white;
      padding: 0 0.8rem;
      color: #3471c9;
      font-size: 1.2rem;
      font-weight: 400;
      opacity: 0.8;
    }

    /* section titles */
    section {
      margin-bottom: 1.8rem;
      animation: fadeSection 0.5s both;
      animation-delay: calc(0.1s * var(--order, 1));
    }

    section h3 {
      font-size: 1.5rem;
      font-weight: 600;
      letter-spacing: -0.2px;
      color: #162b4d;
      margin-bottom: 1.2rem;
      display: inline-block;
      background: linear-gradient(to right, transparent 0%, rgba(64,158,255,0.12) 100%);
      padding: 0.4rem 1.8rem 0.4rem 1rem;
      border-radius: 0 40px 40px 0;
      border-left: 5px solid #3471c9;
      transform: translateX(-5px);
      transition: transform 0.2s;
    }

    section:hover h3 {
      transform: translateX(0);
      background: linear-gradient(to right, rgba(64,158,255,0.18), transparent);
    }

    /* skill chips */
    ul {
      list-style: none;
      margin: 0.5rem 0 0 0;
      padding: 0;
      display: flex;
      flex-wrap: wrap;
      gap: 0.8rem 1.2rem;
    }

    li {
      background: rgba(255,255,255,0.6);
      backdrop-filter: blur(4px);
      padding: 0.3rem 1.2rem 0.3rem 1rem;
      border-radius: 40px;
      font-size: 0.98rem;
      border: 1px solid rgba(64,128,200,0.2);
      box-shadow: 0 2px 5px rgba(0,0,0,0.02);
      transition: all 0.2s;
      flex: 0 1 auto;
    }

    li:hover {
      background: white;
      border-color: #409eff;
      box-shadow: 0 10px 18px -10px #3471c9;
      transform: translateY(-2px);
    }

    li b {
      color: #10325c;
      font-weight: 700;
      margin-right: 0.4rem;
    }

    /* experience & education block styling */
    section p, section b + br + span, section i {
      transition: all 0.2s;
    }

    section b {
      color: #1d3b6f;
      font-size: 1.08rem;
    }

    section i {
      color: #4b5f7a;
      background: rgba(220, 235, 255, 0.5);
      padding: 0.1rem 0.8rem;
      border-radius: 30px;
      font-style: normal;
      font-weight: 500;
      display: inline-block;
      margin: 0.2rem 0 0.5rem 0;
      border: 1px solid #aac8ff;
    }

    /* nested lists inside sections */
    section ul ul, section ul {
      margin-top: 0.3rem;
    }

    section li {
      background: transparent;
      border: none;
      box-shadow: none;
      padding: 0.3rem 0 0.3rem 1.8rem;
      position: relative;
      border-radius: 0;
      width: 100%;
      font-size: 1rem;
      border-bottom: 1px dashed rgba(64,158,255,0.15);
    }

    section li:last-child {
      border-bottom: none;
    }

    section li::before {
      content: "▹";
      position: absolute;
      left: 0;
      color: #409eff;
      font-weight: bold;
      font-size: 1.2rem;
    }

    section li b {
      display: inline-block;
      margin-right: 0.3rem;
    }

    /* project items with tech stack highlight */
    section li i:not(.el-icon) {
      background: #e1efff;
      padding: 0.2rem 1rem;
      border-radius: 40px;
      font-size: 0.9rem;
      font-style: normal;
      color: #0e3e7c;
      margin: 0.2rem 0 0 0;
      display: inline-block;
      border: 1px solid #96bef0;
    }

    /* languages & passions as inline chips */
    section p {
      background: #ecf3fb;
      padding: 1rem 1.5rem;
      border-radius: 48px;
      display: inline-block;
      box-shadow: inset 0 1px 3px #ffffff, 0 4px 10px rgba(64,128,200,0.1);
      font-weight: 500;
      color: #14273e;
    }

    /* special divider remove after last */
    section:last-of-type {
      margin-bottom: 0;
    }

    /* responsive fine-tune */
    @media (max-width: 640px) {
      .header {
        flex-direction: column;
        align-items: flex-start;
        gap: 1rem;
      }
      .profile-pic {
        width: 100px;
        height: 100px;
      }
      .contact-info h2 {
        font-size: 2.2rem;
        border-left-width: 4px;
      }
      .resume-card {
        padding: 1.5rem !important;
      }
      .contact-info p {
        font-size: 0.95rem;
        padding: 0.6rem 1rem;
      }
    }

    /* micro-animations */
    .el-divider, section, .profile-pic, .contact-info p {
      transition: all 0.3s ease;
    }
    .contact-info p:hover {
      background: white;
      box-shadow: 0 12px 22px -12px #2f5597;
    }

    /* section order animation */
    section:nth-of-type(1) { --order: 1; }
    section:nth-of-type(2) { --order: 2; }
    section:nth-of-type(3) { --order: 3; }
    section:nth-of-type(4) { --order: 4; }
    section:nth-of-type(5) { --order: 5; }
    section:nth-of-type(6) { --order: 6; }
    section:nth-of-type(7) { --order: 7; }

    @keyframes fadeSection {
      0% { opacity: 0; transform: translateX(-8px); }
      100% { opacity: 1; transform: translateX(0); }
    }

    /* keep element plus icons inline */
    .el-icon {
      display: inline-flex;
      vertical-align: middle;
    }
  </style>
...existing code...