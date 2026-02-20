<template>
  <div class="resume-app">
    <!-- Animated Background -->
    <div class="animated-bg">
      <div class="gradient-sphere sphere1"></div>
      <div class="gradient-sphere sphere2"></div>
      <div class="gradient-sphere sphere3"></div>
      <div class="grid-overlay"></div>
    </div>

    <!-- Main Container -->
    <div class="resume-container">
      <!-- Floating Navigation Dots -->
      <div class="nav-dots">
        <div 
          v-for="(section, index) in sections" 
          :key="index"
          class="nav-dot"
          :class="{ active: activeSection === index }"
          @click="scrollToSection(index)"
        >
          <span class="dot-tooltip">{{ section }}</span>
        </div>
      </div>

      <!-- Hero Section with Parallax -->
      <el-card shadow="never" class="hero-section glass-card" :body-style="{ padding: '0' }">
        <div class="hero-content">
          <div class="hero-left">
            <el-avatar :size="180" class="hero-avatar">
              <img src="./1000005132.jpg" alt="Pramod N" @error="handleImageError">
            </el-avatar>
            <div class="hero-stats">
              <div class="stat-item">
                <span class="stat-value">5+</span>
                <span class="stat-label">Projects</span>
              </div>
              <div class="stat-item">
                <span class="stat-value">1</span>
                <span class="stat-label">KSCST</span>
              </div>
              <div class="stat-item">
                <span class="stat-value">3</span>
                <span class="stat-label">Languages</span>
              </div>
            </div>
          </div>
          <div class="hero-right">
            <el-tag class="hero-tag" effect="dark" size="large">MCA · Asst. Professor · Researcher</el-tag>
            <h1 class="hero-name">PRAMOD N</h1>
            <div class="hero-contact">
              <el-space wrap :size="16">
                <el-button circle type="info" plain size="large">
                  <el-icon><Phone /></el-icon>
                </el-button>
                <span>+91 8861326592</span>
                <el-divider direction="vertical" />
                <el-button circle type="info" plain size="large">
                  <el-icon><Message /></el-icon>
                </el-button>
                <span>pramod.n1301@gmail.com</span>
                <el-divider direction="vertical" />
                <el-button circle type="info" plain size="large">
                  <el-icon><Link /></el-icon>
                </el-button>
                <a href="https://linkedin.com/in/pramod-n-a965b9264/" target="_blank">linkedin.com/in/pramod-n</a>
              </el-space>
            </div>
          </div>
        </div>
      </el-card>

      <!-- Dashboard Grid -->
      <div class="dashboard-grid">
        <!-- Left Column -->
        <div class="grid-left">
          <!-- Summary Card -->
          <el-card class="dashboard-card glass-card" shadow="hover">
            <template #header>
              <div class="card-header">
                <el-icon><User /></el-icon>
                <span>Professional Summary</span>
              </div>
            </template>
            <div class="summary-content">
              <el-timeline>
                <el-timeline-item
                  v-for="(item, index) in summaryItems"
                  :key="index"
                  :type="item.type"
                  :size="item.size"
                  :hollow="item.hollow"
                >
                  <p>{{ item.text }}</p>
                </el-timeline-item>
              </el-timeline>
            </div>
          </el-card>

          <!-- Skills Card with Progress -->
          <el-card class="dashboard-card glass-card" shadow="hover">
            <template #header>
              <div class="card-header">
                <el-icon><Monitor /></el-icon>
                <span>Technical Expertise</span>
              </div>
            </template>
            <div class="skills-content">
              <el-tabs tab-position="left" class="skills-tabs">
                <el-tab-pane label="Languages">
                  <div v-for="skill in programmingSkills" :key="skill.name" class="skill-progress">
                    <span>{{ skill.name }}</span>
                    <el-progress 
                      :percentage="skill.level" 
                      :color="customColors"
                      :stroke-width="8"
                      striped
                      striped-flow
                    />
                  </div>
                </el-tab-pane>
                <el-tab-pane label="Frameworks">
                  <div v-for="skill in frameworkSkills" :key="skill.name" class="skill-progress">
                    <span>{{ skill.name }}</span>
                    <el-progress 
                      :percentage="skill.level" 
                      :color="customColors"
                      :stroke-width="8"
                      striped
                      striped-flow
                    />
                  </div>
                </el-tab-pane>
                <el-tab-pane label="Tools">
                  <div v-for="skill in toolSkills" :key="skill.name" class="skill-progress">
                    <span>{{ skill.name }}</span>
                    <el-progress 
                      :percentage="skill.level" 
                      :color="customColors"
                      :stroke-width="8"
                      striped
                      striped-flow
                    />
                  </div>
                </el-tab-pane>
              </el-tabs>
            </div>
          </el-card>

          <!-- Languages & Passions -->
          <el-card class="dashboard-card glass-card" shadow="hover">
            <template #header>
              <div class="card-header">
                <el-icon><Collection /></el-icon>
                <span>Languages & Interests</span>
              </div>
            </template>
            <div class="languages-content">
              <el-row :gutter="16">
                <el-col :span="8" v-for="lang in languages" :key="lang.name">
                  <div class="language-item">
                    <el-progress type="dashboard" :percentage="lang.level" :width="80" :stroke-width="6">
                      <template #default>{{ lang.level }}%</template>
                    </el-progress>
                    <span>{{ lang.name }}</span>
                  </div>
                </el-col>
              </el-row>
              <el-divider />
              <div class="passions">
                <el-tag 
                  v-for="passion in passions" 
                  :key="passion"
                  effect="plain"
                  size="large"
                  class="passion-tag"
                >
                  <el-icon><component :is="passion.icon" /></el-icon>
                  {{ passion.name }}
                </el-tag>
              </div>
            </div>
          </el-card>
        </div>

        <!-- Right Column -->
        <div class="grid-right">
          <!-- Experience Card -->
          <el-card class="dashboard-card glass-card" shadow="hover">
            <template #header>
              <div class="card-header">
                <el-icon><Briefcase /></el-icon>
                <span>Professional Journey</span>
                <el-tag class="header-tag" size="small" type="info">2024-2025</el-tag>
              </div>
            </template>
            <div class="timeline-content">
              <el-timeline>
                <el-timeline-item
                  timestamp="Assistant Professor"
                  placement="top"
                  type="primary"
                  size="large"
                >
                  <el-card shadow="never" class="timeline-card">
                    <h4>Department of MCA, NMIT</h4>
                    <p class="timeline-date">August 2024 – July 2025</p>
                    <ul class="timeline-list">
                      <li>Taught core MCA subjects including programming, data structures, and project development</li>
                      <li>Mentored postgraduate students on research-oriented academic projects</li>
                      <li>Participated in academic reviews and curriculum planning meetings</li>
                      <li>Coordinated technical workshops and departmental hackathons</li>
                    </ul>
                  </el-card>
                </el-timeline-item>
              </el-timeline>
            </div>
          </el-card>

          <!-- Education Card -->
          <el-card class="dashboard-card glass-card" shadow="hover">
            <template #header>
              <div class="card-header">
                <el-icon><Reading /></el-icon>
                <span>Academic Background</span>
              </div>
            </template>
            <div class="education-content">
              <el-collapse accordion>
                <el-collapse-item v-for="(edu, index) in education" :key="index" :title="edu.degree">
                  <div class="edu-details">
                    <p><el-icon><School /></el-icon> {{ edu.institution }}</p>
                    <p><el-icon><Calendar /></el-icon> {{ edu.period }}</p>
                    <p><el-icon><DataLine /></el-icon> {{ edu.score }}</p>
                    <p v-if="edu.research"><el-icon><Microscope /></el-icon> {{ edu.research }}</p>
                  </div>
                </el-collapse-item>
              </el-collapse>
            </div>
          </el-card>

          <!-- Projects Card -->
          <el-card class="dashboard-card glass-card" shadow="hover">
            <template #header>
              <div class="card-header">
                <el-icon><DataBoard /></el-icon>
                <span>Innovation Projects</span>
                <el-switch
                  v-model="projectView"
                  active-value="grid"
                  inactive-value="list"
                  active-text="Grid"
                  inactive-text="List"
                />
              </div>
            </template>
            
            <!-- Grid View -->
            <el-row :gutter="16" v-if="projectView === 'grid'">
              <el-col :span="12" v-for="project in projects" :key="project.title">
                <el-card shadow="hover" class="project-card">
                  <div class="project-badge" v-if="project.badge">{{ project.badge }}</div>
                  <h4>{{ project.title }}</h4>
                  <div class="project-tech">
                    <el-tag 
                      v-for="tech in project.tech" 
                      :key="tech"
                      size="small"
                      effect="plain"
                    >{{ tech }}</el-tag>
                  </div>
                  <p>{{ project.description }}</p>
                  <el-button text type="primary" size="small">
                    Details <el-icon><ArrowRight /></el-icon>
                  </el-button>
                </el-card>
              </el-col>
            </el-row>

            <!-- List View -->
            <el-table v-else :data="projects" style="width: 100%" stripe>
              <el-table-column prop="title" label="Project" width="180" />
              <el-table-column prop="tech" label="Tech Stack">
                <template #default="{ row }">
                  <el-tag v-for="t in row.tech" :key="t" size="small">{{ t }}</el-tag>
                </template>
              </el-table-column>
              <el-table-column prop="description" label="Description" />
            </el-table>
          </el-card>
        </div>
      </div>
    </div>

    <!-- Back to Top -->
    <el-backtop :right="30" :bottom="30" />
  </div>
</template>

<script>
import { ref, onMounted } from 'vue'
import { 
  Phone, Message, Link, User, Monitor, Collection, 
  Briefcase, Reading, DataBoard, School, Calendar, 
  DataLine, Microscope, ArrowRight, Plane, Swim, Camera
} from '@element-plus/icons-vue'

export default {
  name: 'App',
  components: {
    Phone, Message, Link, User, Monitor, Collection,
    Briefcase, Reading, DataBoard, School, Calendar,
    DataLine, Microscope, ArrowRight
  },
  setup() {
    const activeSection = ref(0)
    const projectView = ref('grid')
    
    const sections = ['Summary', 'Skills', 'Experience', 'Education', 'Projects']
    
    const customColors = [
      { color: '#409EFF', percentage: 20 },
      { color: '#67C23A', percentage: 40 },
      { color: '#E6A23C', percentage: 60 },
      { color: '#F56C6C', percentage: 80 },
      { color: '#909399', percentage: 100 }
    ]

    const summaryItems = [
      { text: 'Motivated academic and developer with experience as Assistant Professor', type: 'primary', size: 'large' },
      { text: 'Strong foundation in computer applications', type: 'success' },
      { text: 'Passionate about teaching, research, and innovative projects', type: 'warning' },
      { text: 'Ph.D. candidate in IoT with Blockchain', type: 'info', hollow: true }
    ]

    const programmingSkills = [
      { name: 'Java', level: 85 },
      { name: 'Python', level: 80 },
      { name: 'JavaScript', level: 75 },
      { name: 'SQL', level: 80 }
    ]

    const frameworkSkills = [
      { name: 'Node.js', level: 75 },
      { name: 'Express.js', level: 70 },
      { name: 'Android', level: 75 },
      { name: 'WebRTC', level: 65 }
    ]

    const toolSkills = [
      { name: 'Firebase', level: 80 },
      { name: 'Git', level: 85 },
      { name: 'Postman', level: 75 },
      { name: 'Figma', level: 70 }
    ]

    const languages = [
      { name: 'Kannada', level: 100 },
      { name: 'Hindi', level: 85 },
      { name: 'English', level: 80 }
    ]

    const passions = [
      { name: 'Travelling', icon: 'Plane' },
      { name: 'Swimming', icon: 'Swim' },
      { name: 'Photography', icon: 'Camera' }
    ]

    const education = [
      {
        degree: 'Ph.D. (Computer Science)',
        institution: 'Nitte Meenakshi Institute of Technology',
        period: '2025 - Present',
        score: 'Ongoing',
        research: 'Internet of Things (IoT) with Blockchain'
      },
      {
        degree: 'Master of Computer Applications',
        institution: 'BMS Institute of Technology, Bengaluru',
        period: '2022 – 2024',
        score: 'CGPA: 7.4/10'
      },
      {
        degree: 'Bachelor of Science',
        institution: 'MES Degree College, Bengaluru',
        period: '2019 – 2022',
        score: 'CGPA: 7.4/10'
      },
      {
        degree: 'PUC',
        institution: 'St. Claret PU College, Bengaluru',
        period: '2017 – 2019',
        score: 'Percentage: 65%'
      },
      {
        degree: 'SSLC',
        institution: 'Ideal English High School, Bengaluru',
        period: '2004 – 2017',
        score: 'Percentage: 87%'
      }
    ]

    const projects = [
      {
        title: 'Smart Doctor',
        tech: ['Java', 'Android', 'Firebase', 'SQL'],
        description: 'Healthcare mobile app with smart diagnosis',
        badge: 'KSCST Shortlisted'
      },
      {
        title: 'Driver Drowsiness Alert',
        tech: ['Python', 'OpenCV', 'ML'],
        description: 'Real-time fatigue detection system'
      },
      {
        title: 'Video Conference App',
        tech: ['Node.js', 'WebRTC', 'Firebase'],
        description: 'Cross-platform video conferencing'
      },
      {
        title: 'AQI Analysis App',
        tech: ['Python', 'REST API', 'Android'],
        description: 'Air quality monitoring dashboard'
      },
      {
        title: 'E-Library System',
        tech: ['Node.js', 'Express', 'SQL'],
        description: 'Digital library management'
      }
    ]

    const scrollToSection = (index) => {
      activeSection.value = index
      // Implement scroll logic
    }

    const handleImageError = (e) => {
      e.target.src = 'https://via.placeholder.com/180x180?text=PN'
    }

    return {
      activeSection,
      projectView,
      sections,
      customColors,
      summaryItems,
      programmingSkills,
      frameworkSkills,
      toolSkills,
      languages,
      passions,
      education,
      projects,
      scrollToSection,
      handleImageError
    }
  }
}
</script>

<style scoped>
.resume-app {
  min-height: 100vh;
  background: #0a0f1e;
  position: relative;
  overflow-x: hidden;
  font-family: 'Inter', sans-serif;
}

/* Animated Background */
.animated-bg {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: 0;
  pointer-events: none;
}

.gradient-sphere {
  position: absolute;
  border-radius: 50%;
  filter: blur(80px);
  opacity: 0.4;
  animation: floatSphere 20s infinite alternate;
}

.sphere1 {
  width: 500px;
  height: 500px;
  background: #409EFF;
  top: -200px;
  right: -200px;
  animation-delay: 0s;
}

.sphere2 {
  width: 600px;
  height: 600px;
  background: #7928ca;
  bottom: -300px;
  left: -200px;
  animation-delay: 2s;
}

.sphere3 {
  width: 400px;
  height: 400px;
  background: #ff4d4d;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  animation-delay: 4s;
}

.grid-overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-image: 
    linear-gradient(rgba(64, 158, 255, 0.05) 1px, transparent 1px),
    linear-gradient(90deg, rgba(64, 158, 255, 0.05) 1px, transparent 1px);
  background-size: 50px 50px;
}

@keyframes floatSphere {
  0% { transform: translate(0, 0) scale(1); }
  100% { transform: translate(100px, 50px) scale(1.2); }
}

/* Main Container */
.resume-container {
  position: relative;
  z-index: 1;
  max-width: 1400px;
  margin: 0 auto;
  padding: 2rem;
}

/* Navigation Dots */
.nav-dots {
  position: fixed;
  right: 30px;
  top: 50%;
  transform: translateY(-50%);
  display: flex;
  flex-direction: column;
  gap: 15px;
  z-index: 100;
}

.nav-dot {
  width: 12px;
  height: 12px;
  border-radius: 50%;
  background: rgba(255, 255, 255, 0.3);
  cursor: pointer;
  transition: all 0.3s;
  position: relative;
}

.nav-dot:hover, .nav-dot.active {
  background: #409EFF;
  transform: scale(1.5);
}

.nav-dot:hover .dot-tooltip {
  opacity: 1;
  transform: translateX(-10px);
}

.dot-tooltip {
  position: absolute;
  right: 25px;
  top: 50%;
  transform: translateY(-50%);
  background: rgba(0, 0, 0, 0.8);
  color: white;
  padding: 4px 8px;
  border-radius: 4px;
  font-size: 12px;
  white-space: nowrap;
  opacity: 0;
  transition: all 0.3s;
  pointer-events: none;
}

/* Glass Card Effect */
.glass-card {
  background: rgba(255, 255, 255, 0.1) !important;
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.1) !important;
  border-radius: 24px !important;
  transition: all 0.3s;
}

.glass-card:hover {
  background: rgba(255, 255, 255, 0.15) !important;
  border-color: rgba(64, 158, 255, 0.3) !important;
  transform: translateY(-2px);
}

/* Hero Section */
.hero-section {
  margin-bottom: 2rem;
  overflow: hidden;
  background: rgba(0, 0, 0, 0.3) !important;
}

.hero-content {
  display: flex;
  padding: 2rem;
  gap: 3rem;
  align-items: center;
}

.hero-left {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1.5rem;
}

.hero-avatar {
  border: 4px solid #409EFF;
  animation: pulse 2s infinite;
}

@keyframes pulse {
  0% { box-shadow: 0 0 0 0 rgba(64, 158, 255, 0.4); }
  70% { box-shadow: 0 0 0 10px rgba(64, 158, 255, 0); }
  100% { box-shadow: 0 0 0 0 rgba(64, 158, 255, 0); }
}

.hero-stats {
  display: flex;
  gap: 2rem;
  margin-top: 1rem;
}

.stat-item {
  text-align: center;
}

.stat-value {
  display: block;
  font-size: 1.5rem;
  font-weight: bold;
  color: #409EFF;
}

.stat-label {
  font-size: 0.9rem;
  color: rgba(255, 255, 255, 0.7);
}

.hero-right {
  flex: 1;
}

.hero-tag {
  margin-bottom: 1rem;
  background: linear-gradient(90deg, #409EFF, #7928ca) !important;
  border: none !important;
}

.hero-name {
  font-size: 3.5rem;
  font-weight: 800;
  background: linear-gradient(135deg, #fff, #409EFF);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  margin: 0.5rem 0;
  letter-spacing: -0.02em;
}

.hero-contact {
  color: rgba(255, 255, 255, 0.8);
}

.hero-contact a {
  color: #409EFF;
  text-decoration: none;
}

/* Dashboard Grid */
.dashboard-grid {
  display: grid;
  grid-template-columns: 1fr 1.5fr;
  gap: 1.5rem;
}

.grid-left, .grid-right {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

/* Dashboard Cards */
.dashboard-card {
  width: 100%;
}

.card-header {
  display: flex;
  align-items: center;
  gap: 10px;
  font-size: 1.2rem;
  font-weight: 600;
  color: white;
}

.card-header .el-icon {
  font-size: 1.5rem;
  color: #409EFF;
}

.header-tag {
  margin-left: auto;
}

/* Skills Section */
.skills-tabs :deep(.el-tabs__item) {
  color: rgba(255, 255, 255, 0.7);
}

.skills-tabs :deep(.el-tabs__item.is-active) {
  color: #409EFF;
}

.skill-progress {
  margin-bottom: 1rem;
}

.skill-progress span {
  display: block;
  margin-bottom: 0.5rem;
  color: white;
}

/* Languages Section */
.language-item {
  text-align: center;
  color: white;
}

.language-item span {
  display: block;
  margin-top: 0.5rem;
}

.passions {
  display: flex;
  gap: 1rem;
  flex-wrap: wrap;
  justify-content: center;
}

.passion-tag {
  padding: 0.5rem 1rem !important;
  background: rgba(64, 158, 255, 0.1) !important;
  border-color: #409EFF !important;
  color: white !important;
}

.passion-tag .el-icon {
  margin-right: 5px;
}

/* Timeline */
.timeline-card {
  background: rgba(255, 255, 255, 0.05) !important;
  border: none !important;
}

.timeline-date {
  color: #409EFF;
  font-size: 0.9rem;
  margin: 0.5rem 0;
}

.timeline-list {
  color: rgba(255, 255, 255, 0.8);
  padding-left: 1.2rem;
}

.timeline-list li {
  margin-bottom: 0.5rem;
}

/* Education */
.edu-details {
  color: rgba(255, 255, 255, 0.8);
}

.edu-details p {
  display: flex;
  align-items: center;
  gap: 8px;
  margin: 0.5rem 0;
}

/* Projects */
.project-card {
  background: rgba(255, 255, 255, 0.05) !important;
  border: none !important;
  margin-bottom: 1rem;
  position: relative;
  overflow: hidden;
}

.project-badge {
  position: absolute;
  top: 10px;
  right: -30px;
  background: #F56C6C;
  color: white;
  padding: 4px 30px;
  transform: rotate(45deg);
  font-size: 0.8rem;
}

.project-card h4 {
  color: white;
  margin: 0 0 0.5rem 0;
}

.project-tech {
  display: flex;
  gap: 0.5rem;
  flex-wrap: wrap;
  margin: 0.5rem 0;
}

.project-card p {
  color: rgba(255, 255, 255, 0.7);
  font-size: 0.9rem;
}

/* Responsive Design */
@media (max-width: 1024px) {
  .dashboard-grid {
    grid-template-columns: 1fr;
  }
  
  .hero-content {
    flex-direction: column;
    text-align: center;
  }
  
  .hero-name {
    font-size: 2.5rem;
  }
  
  .nav-dots {
    display: none;
  }
}
</style>