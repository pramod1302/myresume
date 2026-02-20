<template>
  <div class="resume-container">
    <el-card shadow="hover" class="resume-card">
      <div class="header">
        <img class="profile-pic" :src="require('./1000005132.jpg')" alt="Profile Picture" />
        <div class="contact-info">
          <h2>PRAMOD N</h2>
          <p>
            <el-icon><i class="el-icon-phone"></i></el-icon> 8861326592 |
            <el-icon><i class="el-icon-message"></i></el-icon> pramod.n1301@gmail.com |
            <el-icon><i class="el-icon-link"></i></el-icon>
            <a href="https://linkedin.com/in/pramod-n-a965b9264/" target="_blank">linkedin.com/in/pramod-n-a965b9264/</a> |
            Bangalore, KA
          </p>
        </div>
      </div>
      <el-divider></el-divider>
      <section>
        <h3>SUMMARY</h3>
        <p>
          Motivated and detail-oriented academic and developer with experience as an Assistant Professor and a strong foundation in computer applications. Passionate about teaching, research, and contributing to innovative projects. Eager to leverage technical, academic, and research skills in dynamic environments.
        </p>
      </section>
      <el-divider></el-divider>
      <section>
        <h3>SKILLS</h3>
        <ul>
          <li><b>Programming Languages:</b> Java, C, Python, SQL, JavaScript</li>
          <li><b>Web & App Development:</b> Full Stack Development, Node.js, Express.js, Android Studio, Web Technologies</li>
          <li><b>Databases & Cloud:</b> Firebase, AWS Lambda, SQL</li>
          <li><b>Hosting & Deployment:</b> Vercel (static web hosting), Render</li>
          <li><b>Testing & Tools:</b> Postman API Testing, cURL Testing, Selenium</li>
          <li><b>UI/UX Design:</b> Figma, Photoshop, Premiere Pro</li>
          <li><b>Other Tools:</b> HTML, Git & GitHub</li>
        </ul>
      </section>
      <el-divider></el-divider>
      <section>
        <h3>EXPERIENCE</h3>
        <b>Assistant Professor</b><br>
        Department of MCA, Nitte Meenakshi Institute of Technology, Bengaluru, KA<br>
        <i>August 2024 – July 2025</i>
        <ul>
          <li>Taught core MCA subjects including programming, data structures, and project development.</li>
          <li>Mentored postgraduate students on research-oriented academic projects.</li>
          <li>Participated in academic reviews and curriculum planning meetings.</li>
          <li>Assisted in departmental event coordination and student technical workshops.</li>
        </ul>
      </section>
      <el-divider></el-divider>
      <section>
        <h3>EDUCATION</h3>
        <ul>
          <li>
            <b>Ph.D. (Computer Science)</b> – Started in 2025<br>
            Research Centre: Nitte Meenakshi Institute of Technology, Bengaluru, KA<br>
            Research Area: Internet of Things (IoT) with Blockchain
          </li>
          <li>
            <b>Master of Computer Applications (MCA)</b> | 2022 – 2024<br>
            BMS Institute of Technology, Bengaluru, KA<br>
            CGPA: 7.4 / 10
          </li>
          <li>
            <b>Bachelor of Science</b> | 2019 – 2022<br>
            MES Degree College, Bengaluru, KA<br>
            CGPA: 7.4 / 10
          </li>
          <li>
            <b>PUC</b> | 2017 – 2019<br>
            St. Claret PU College, Bengaluru, KA<br>
            Percentage: 65 / 100
          </li>
          <li>
            <b>SSLC</b> | 2004 – 2017<br>
            Ideal English High School, Bengaluru, KA<br>
            Percentage: 87 / 100
          </li>
        </ul>
      </section>
      <el-divider></el-divider>
      <section>
        <h3>PROJECTS</h3>
        <ul>
          <li>
            <b>Smart Doctor</b> – Shortlisted for 47th KSCST Student Project Programme<br>
            <i>Tech Stack:</i> Java, Android Studio, Firebase, SQL<br>
            Built a healthcare mobile application providing smart diagnosis and doctor consultation support.
          </li>
          <li>
            <b>Driver Drowsiness Alert System</b><br>
            <i>Tech Stack:</i> Python, OpenCV, Machine Learning<br>
            Developed a computer vision–based system to detect driver fatigue and alert in real-time.
          </li>
          <li>
            <b>Video Conference Mobile Application</b><br>
            <i>Tech Stack:</i> Node.js, Express.js, Firebase, WebRTC, Render<br>
            Created a cross-platform video conferencing app with real-time chat and secure authentication.
          </li>
          <li>
            <b>Air Quality Index (AQI) Analysis Mobile Application</b><br>
            <i>Tech Stack:</i> Python, Firebase, REST APIs, Android Studio<br>
            Designed an app to fetch and analyze AQI data, displaying pollution levels in a user-friendly dashboard.
          </li>
          <li>
            <b>E-Library Management System</b><br>
            <i>Tech Stack:</i> Full Stack (Node.js, Express.js, Firebase, SQL)<br>
            Built a digital library system enabling book management, student access, and admin controls.
          </li>
        </ul>
      </section>
      <el-divider></el-divider>
      <section>
        <h3>LANGUAGES</h3>
        <p>Kannada: Native | Hindi: Proficient | English: Proficient</p>
      </section>
      <el-divider></el-divider>
      <section>
        <h3>PASSIONS</h3>
        <p>Travelling, Swimming, Photography</p>
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
.resume-container {
  background: #f5f7fa;
  min-height: 100vh;
  padding: 40px 0;
}
.resume-card {
  max-width: 900px;
  margin: 0 auto;
  padding: 32px;
}
.header {
  display: flex;
  align-items: center;
  margin-bottom: 16px;
}
.profile-pic {
  width: 120px;
  height: 120px;
  object-fit: cover;
  border-radius: 60px;
  margin-right: 32px;
  border: 3px solid #409EFF;
}
.contact-info h2 {
  margin: 0 0 8px 0;
}
.contact-info p {
  margin: 0;
  font-size: 15px;
  color: #606266;
}
section {
  margin-bottom: 18px;
}
ul {
  margin: 0 0 0 18px;
  padding: 0;
}
</style>
