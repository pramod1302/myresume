<template>
  <div class="professional-resume">
    <!-- Premium Background with Subtle Pattern -->
    <div class="premium-bg">
      <div class="bg-pattern"></div>
      <div class="bg-gradient"></div>
    </div>

    <!-- Main Content -->
    <div class="resume-layout">
      <!-- Sidebar Navigation -->
      <aside class="sidebar" :class="{ 'sidebar-collapsed': isSidebarCollapsed }">
        <div class="sidebar-header">
          <div class="profile-mini">
            <el-avatar :size="isSidebarCollapsed ? 40 : 80" class="profile-mini-avatar">
              <img src="./1000005132.jpg" alt="Pramod N" @error="handleImageError">
            </el-avatar>
            <div v-if="!isSidebarCollapsed" class="profile-mini-info">
              <h3>Pramod N</h3>
              <p>Asst. Professor · MCA</p>
            </div>
          </div>
          <el-button 
            :icon="isSidebarCollapsed ? Expand : Fold" 
            @click="toggleSidebar"
            class="sidebar-toggle"
            text
          />
        </div>

        <el-menu
          :default-active="activeMenu"
          class="sidebar-menu"
          :collapse="isSidebarCollapsed"
          :collapse-transition="true"
          @select="handleMenuSelect"
        >
          <el-menu-item index="summary">
            <el-icon><Document /></el-icon>
            <span>Summary</span>
          </el-menu-item>
          <el-menu-item index="skills">
            <el-icon><Monitor /></el-icon>
            <span>Skills</span>
          </el-menu-item>
          <el-menu-item index="experience">
            <el-icon><Briefcase /></el-icon>
            <span>Experience</span>
          </el-menu-item>
          <el-menu-item index="education">
            <el-icon><Reading /></el-icon>
            <span>Education</span>
          </el-menu-item>
          <el-menu-item index="projects">
            <el-icon><DataBoard /></el-icon>
            <span>Projects</span>
          </el-menu-item>
          <el-menu-item index="achievements">
            <el-icon><Trophy /></el-icon>
            <span>Achievements</span>
          </el-menu-item>
        </el-menu>

        <div v-if="!isSidebarCollapsed" class="sidebar-footer">
          <div class="availability-badge">
            <span class="status-dot"></span>
            Available for opportunities
          </div>
          <div class="sidebar-contact">
            <el-tooltip content="Email" placement="right">
              <el-button circle size="small" @click="copyToClipboard('pramod.n1301@gmail.com')">
                <el-icon><Message /></el-icon>
              </el-button>
            </el-tooltip>
            <el-tooltip content="LinkedIn" placement="right">
              <el-button circle size="small" @click="openLink('https://linkedin.com/in/pramod-n-a965b9264/')">
                <el-icon><Link /></el-icon>
              </el-button>
            </el-tooltip>
            <el-tooltip content="Download Resume" placement="right">
              <el-button circle size="small">
                <el-icon><Download /></el-icon>
              </el-button>
            </el-tooltip>
          </div>
        </div>
      </aside>

      <!-- Main Content Area -->
      <main class="main-content" ref="mainContent">
        <!-- Hero Banner -->
        <section class="hero-banner">
          <div class="hero-banner-content">
            <el-row :gutter="24" align="middle">
              <el-col :xs="24" :sm="24" :md="16" :lg="16">
                <div class="hero-text">
                  <el-tag class="hero-greeting" size="large" effect="plain">👋 Welcome to my portfolio</el-tag>
                  <h1>Pramod N</h1>
                  <h2>Assistant Professor & Full Stack Developer</h2>
                  <p class="hero-bio">
                    Bridging academia and industry with 5+ innovative projects. 
                    Ph.D. candidate in IoT & Blockchain. Passionate about mentoring 
                    and building scalable solutions.
                  </p>
                  <div class="hero-actions">
                    <el-button type="primary" size="large" @click="scrollToSection('projects')">
                      View Projects
                      <el-icon><ArrowRight /></el-icon>
                    </el-button>
                    <el-button size="large" @click="scrollToSection('contact')">
                      Contact Me
                    </el-button>
                  </div>
                </div>
              </el-col>
              <el-col :xs="24" :sm="24" :md="8" :lg="8">
                <div class="hero-stats-grid">
                  <div class="stat-card">
                    <span class="stat-number">5+</span>
                    <span class="stat-label">Projects</span>
                  </div>
                  <div class="stat-card">
                    <span class="stat-number">1</span>
                    <span class="stat-label">KSCST</span>
                  </div>
                  <div class="stat-card">
                    <span class="stat-number">3</span>
                    <span class="stat-label">Languages</span>
                  </div>
                  <div class="stat-card">
                    <span class="stat-number">2+</span>
                    <span class="stat-label">Years</span>
                  </div>
                </div>
              </el-col>
            </el-row>
          </div>
        </section>

        <!-- Summary Section -->
        <section id="summary" class="content-section" ref="summary">
          <div class="section-header">
            <h3>Professional Summary</h3>
            <el-divider direction="horizontal" />
          </div>
          <el-row :gutter="24">
            <el-col :span="16">
              <el-card class="summary-card" shadow="hover">
                <p class="summary-text">
                  Motivated academic and developer with experience as an Assistant Professor 
                  and a strong foundation in computer applications. Passionate about teaching, 
                  research, and contributing to innovative projects. Eager to leverage technical, 
                  academic, and research skills in dynamic environments.
                </p>
                <div class="summary-highlights">
                  <el-tag v-for="item in summaryHighlights" :key="item" effect="plain">
                    {{ item }}
                  </el-tag>
                </div>
              </el-card>
            </el-col>
            <el-col :span="8">
              <el-card class="contact-card" shadow="hover">
                <div class="contact-item">
                  <el-icon><Phone /></el-icon>
                  <span>+91 8861326592</span>
                </div>
                <div class="contact-item">
                  <el-icon><Message /></el-icon>
                  <span>pramod.n1301@gmail.com</span>
                </div>
                <div class="contact-item">
                  <el-icon><Location /></el-icon>
                  <span>Bangalore, KA</span>
                </div>
                <div class="contact-item">
                  <el-icon><Link /></el-icon>
                  <a href="https://linkedin.com/in/pramod-n-a965b9264/" target="_blank">
                    linkedin.com/in/pramod-n
                  </a>
                </div>
              </el-card>
            </el-col>
          </el-row>
        </section>

        <!-- Skills Section -->
        <section id="skills" class="content-section" ref="skills">
          <div class="section-header">
            <h3>Technical Expertise</h3>
            <el-divider direction="horizontal" />
          </div>
          
          <el-row :gutter="24">
            <el-col :span="8" v-for="category in skillCategories" :key="category.title">
              <el-card class="skill-category-card" shadow="hover">
                <template #header>
                  <div class="skill-category-header">
                    <el-icon><component :is="category.icon" /></el-icon>
                    <span>{{ category.title }}</span>
                  </div>
                </template>
                <div class="skill-items">
                  <div v-for="skill in category.skills" :key="skill.name" class="skill-item">
                    <div class="skill-info">
                      <span>{{ skill.name }}</span>
                      <span class="skill-level">{{ skill.level }}%</span>
                    </div>
                    <el-progress 
                      :percentage="skill.level" 
                      :color="progressColor"
                      :stroke-width="6"
                      :show-text="false"
                    />
                  </div>
                </div>
              </el-card>
            </el-col>
          </el-row>
        </section>

        <!-- Experience & Education Combined -->
        <section id="experience" class="content-section" ref="experience">
          <el-row :gutter="24">
            <el-col :span="12">
              <div class="section-header">
                <h3>Work Experience</h3>
                <el-divider direction="horizontal" />
              </div>
              <el-timeline>
                <el-timeline-item
                  v-for="exp in experiences"
                  :key="exp.title"
                  :type="exp.type"
                  :size="exp.size"
                  :icon="exp.icon"
                  :timestamp="exp.period"
                  placement="top"
                >
                  <el-card class="experience-card" shadow="hover">
                    <h4>{{ exp.title }}</h4>
                    <p class="exp-company">{{ exp.company }}</p>
                    <ul class="exp-description">
                      <li v-for="item in exp.description" :key="item">{{ item }}</li>
                    </ul>
                  </el-card>
                </el-timeline-item>
              </el-timeline>
            </el-col>
            
            <el-col :span="12">
              <div class="section-header">
                <h3>Education</h3>
                <el-divider direction="horizontal" />
              </div>
              <div class="education-timeline">
                <div v-for="(edu, index) in education" :key="edu.degree" class="edu-item">
                  <div class="edu-marker" :class="{ 'active': index === 0 }"></div>
                  <el-card class="education-card" shadow="hover">
                    <div class="edu-header">
                      <h4>{{ edu.degree }}</h4>
                      <el-tag size="small" :type="index === 0 ? 'danger' : 'info'">
                        {{ edu.score }}
                      </el-tag>
                    </div>
                    <p class="edu-institution">{{ edu.institution }}</p>
                    <p class="edu-period">{{ edu.period }}</p>
                    <p v-if="edu.research" class="edu-research">
                      <el-icon><Microscope /></el-icon>
                      {{ edu.research }}
                    </p>
                  </el-card>
                </div>
              </div>
            </el-col>
          </el-row>
        </section>

        <!-- Projects Section -->
        <section id="projects" class="content-section" ref="projects">
          <div class="section-header">
            <h3>Innovation Projects</h3>
            <el-divider direction="horizontal" />
          </div>

          <el-tabs v-model="projectView" class="project-tabs">
            <el-tab-pane label="Grid View" name="grid">
              <el-row :gutter="24">
                <el-col :xs="24" :sm="12" :md="8" v-for="project in projects" :key="project.title">
                  <el-card class="project-card" shadow="hover" :body-style="{ padding: '0' }">
                    <div class="project-image">
                      <el-image :src="project.image" fit="cover">
                        <template #error>
                          <div class="image-error">
                            <el-icon><Picture /></el-icon>
                          </div>
                        </template>
                      </el-image>
                      <div class="project-badge" v-if="project.badge">{{ project.badge }}</div>
                    </div>
                    <div class="project-content">
                      <h4>{{ project.title }}</h4>
                      <p>{{ project.description }}</p>
                      <div class="project-tech">
                        <el-tag 
                          v-for="tech in project.tech" 
                          :key="tech"
                          size="small"
                          effect="plain"
                        >{{ tech }}</el-tag>
                      </div>
                      <el-button text type="primary" class="project-link">
                        Learn more <el-icon><ArrowRight /></el-icon>
                      </el-button>
                    </div>
                  </el-card>
                </el-col>
              </el-row>
            </el-tab-pane>
            
            <el-tab-pane label="List View" name="list">
              <el-table :data="projects" style="width: 100%" stripe>
                <el-table-column prop="title" label="Project" width="200" />
                <el-table-column prop="tech" label="Tech Stack">
                  <template #default="{ row }">
                    <el-tag 
                      v-for="t in row.tech" 
                      :key="t" 
                      size="small" 
                      effect="plain"
                      class="tech-tag"
                    >{{ t }}</el-tag>
                  </template>
                </el-table-column>
                <el-table-column prop="description" label="Description" />
                <el-table-column label="Badge" width="120">
                  <template #default="{ row }">
                    <el-tag v-if="row.badge" type="danger" size="small">{{ row.badge }}</el-tag>
                  </template>
                </el-table-column>
              </el-table>
            </el-tab-pane>
          </el-tabs>
        </section>

        <!-- Achievements Section -->
        <section id="achievements" class="content-section" ref="achievements">
          <div class="section-header">
            <h3>Achievements & Recognition</h3>
            <el-divider direction="horizontal" />
          </div>

          <el-row :gutter="24">
            <el-col :span="8" v-for="achievement in achievements" :key="achievement.title">
              <el-card class="achievement-card" shadow="hover">
                <el-icon class="achievement-icon"><component :is="achievement.icon" /></el-icon>
                <h4>{{ achievement.title }}</h4>
                <p>{{ achievement.description }}</p>
                <el-tag size="small">{{ achievement.year }}</el-tag>
              </el-card>
            </el-col>
          </el-row>
        </section>

        <!-- Call to Action -->
        <section id="contact" class="content-section cta-section">
          <el-card class="cta-card" shadow="hover">
            <el-row :gutter="24" align="middle">
              <el-col :span="16">
                <h3>Interested in collaboration?</h3>
                <p>I'm always open to discussing research opportunities, teaching positions, or innovative projects.</p>
              </el-col>
              <el-col :span="8" class="cta-actions">
                <el-button type="primary" size="large" @click="openEmail">
                  <el-icon><Message /></el-icon>
                  Send Message
                </el-button>
                <el-button size="large" @click="downloadResume">
                  <el-icon><Download /></el-icon>
                  Resume
                </el-button>
              </el-col>
            </el-row>
          </el-card>
        </section>
      </main>
    </div>

    <!-- Back to Top -->
    <el-backtop :right="30" :bottom="30" />
  </div>
</template>

<script>
import { ref, reactive, onMounted, nextTick } from 'vue'
import { 
  Document, Monitor, Briefcase, Reading, DataBoard, 
  Trophy, Message, Link, Download, ArrowRight, Phone,
  Location, Picture, Microscope, Expand, Fold,
  Star, Medal, TrendCharts, Calendar, School, DataLine
} from '@element-plus/icons-vue'

export default {
  name: 'ProfessionalResume',
  components: {
    Document, Monitor, Briefcase, Reading, DataBoard,
    Trophy, Message, Link, Download, ArrowRight, Phone,
    Location, Picture, Microscope, Expand, Fold,
    Star, Medal, TrendCharts, Calendar, School, DataLine
  },
  setup() {
    const isSidebarCollapsed = ref(false)
    const activeMenu = ref('summary')
    const projectView = ref('grid')
    const mainContent = ref(null)
    
    const summary = ref(null)
    const skills = ref(null)
    const experience = ref(null)
    const projects = ref(null)
    const achievements = ref(null)

    const toggleSidebar = () => {
      isSidebarCollapsed.value = !isSidebarCollapsed.value
    }

    const handleMenuSelect = (index) => {
      activeMenu.value = index
      scrollToSection(index)
    }

    const scrollToSection = (section) => {
      const element = document.getElementById(section)
      if (element) {
        element.scrollIntoView({ behavior: 'smooth', block: 'start' })
      }
    }

    const progressColor = [
      { color: '#f56c6c', percentage: 60 },
      { color: '#e6a23c', percentage: 70 },
      { color: '#67c23a', percentage: 80 },
      { color: '#409eff', percentage: 100 }
    ]

    const summaryHighlights = [
      'Academic Experience',
      'Full Stack Development',
      'Research Oriented',
      'Project Mentor'
    ]

    const skillCategories = [
      {
        title: 'Programming Languages',
        icon: 'Document',
        skills: [
          { name: 'Java', level: 85 },
          { name: 'Python', level: 80 },
          { name: 'JavaScript', level: 75 },
          { name: 'SQL', level: 80 }
        ]
      },
      {
        title: 'Frameworks & Libraries',
        icon: 'Monitor',
        skills: [
          { name: 'Node.js', level: 75 },
          { name: 'Express.js', level: 70 },
          { name: 'Android', level: 75 },
          { name: 'WebRTC', level: 65 }
        ]
      },
      {
        title: 'Tools & Platforms',
        icon: 'DataBoard',
        skills: [
          { name: 'Firebase', level: 80 },
          { name: 'Git', level: 85 },
          { name: 'Postman', level: 75 },
          { name: 'Figma', level: 70 }
        ]
      }
    ]

    const experiences = [
      {
        title: 'Assistant Professor',
        company: 'Department of MCA, Nitte Meenakshi Institute of Technology',
        period: 'August 2024 – July 2025',
        type: 'primary',
        size: 'large',
        icon: Briefcase,
        description: [
          'Taught core MCA subjects including programming, data structures, and project development',
          'Mentored postgraduate students on research-oriented academic projects',
          'Participated in academic reviews and curriculum planning meetings',
          'Coordinated technical workshops and departmental hackathons'
        ]
      }
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
        score: '65%'
      },
      {
        degree: 'SSLC',
        institution: 'Ideal English High School, Bengaluru',
        period: '2004 – 2017',
        score: '87%'
      }
    ]

    const projects = [
      {
        title: 'Smart Doctor',
        tech: ['Java', 'Android', 'Firebase', 'SQL'],
        description: 'Healthcare mobile app with smart diagnosis and doctor consultation support',
        badge: 'KSCST Shortlisted',
        image: 'https://via.placeholder.com/300x200?text=Smart+Doctor'
      },
      {
        title: 'Driver Drowsiness Alert',
        tech: ['Python', 'OpenCV', 'ML'],
        description: 'Computer vision–based system to detect driver fatigue and alert in real-time',
        image: 'https://via.placeholder.com/300x200?text=Drowsiness+Alert'
      },
      {
        title: 'Video Conference App',
        tech: ['Node.js', 'Express.js', 'Firebase', 'WebRTC'],
        description: 'Cross-platform video conferencing app with real-time chat',
        image: 'https://via.placeholder.com/300x200?text=Video+Conf'
      },
      {
        title: 'AQI Analysis App',
        tech: ['Python', 'Firebase', 'REST APIs', 'Android'],
        description: 'Fetch and analyze AQI data with user-friendly dashboard',
        image: 'https://via.placeholder.com/300x200?text=AQI+Analysis'
      },
      {
        title: 'E-Library System',
        tech: ['Node.js', 'Express.js', 'Firebase', 'SQL'],
        description: 'Digital library system enabling book management and student access',
        image: 'https://via.placeholder.com/300x200?text=E-Library'
      }
    ]

    const achievements = [
      {
        title: 'KSCST Shortlist',
        description: 'Smart Doctor project shortlisted for 47th KSCST Student Project Programme',
        icon: 'Trophy',
        year: '2024'
      },
      {
        title: 'Research Publication',
        description: 'Paper on IoT-Blockchain integration in progress',
        icon: 'Medal',
        year: '2025'
      },
      {
        title: 'Academic Excellence',
        description: '87% in SSLC with distinction',
        icon: 'Star',
        year: '2017'
      }
    ]

    const handleImageError = (e) => {
      e.target.src = 'https://via.placeholder.com/180x180?text=PN'
    }

    const copyToClipboard = (text) => {
      navigator.clipboard.writeText(text)
      ElMessage.success('Copied to clipboard!')
    }

    const openLink = (url) => {
      window.open(url, '_blank')
    }

    const openEmail = () => {
      window.location.href = 'mailto:pramod.n1301@gmail.com'
    }

    const downloadResume = () => {
      // Implement resume download
      ElMessage.info('Resume download started')
    }

    return {
      isSidebarCollapsed,
      activeMenu,
      projectView,
      mainContent,
      summary,
      skills,
      experience,
      education,
      projects,
      achievements,
      toggleSidebar,
      handleMenuSelect,
      scrollToSection,
      progressColor,
      summaryHighlights,
      skillCategories,
      experiences,
      education,
      projects,
      achievements,
      handleImageError,
      copyToClipboard,
      openLink,
      openEmail,
      downloadResume,
      Expand,
      Fold,
      Document,
      Monitor,
      Briefcase,
      Reading,
      DataBoard,
      Trophy,
      Message,
      Link,
      Download,
      ArrowRight,
      Phone,
      Location,
      Picture,
      Microscope,
      Star,
      Medal,
      TrendCharts,
      Calendar,
      School,
      DataLine
    }
  }
}
</script>

<style scoped>
.professional-resume {
  min-height: 100vh;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  position: relative;
  font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
}

/* Premium Background */
.premium-bg {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: 0;
}

.bg-pattern {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-image: radial-gradient(circle at 30% 40%, rgba(255,255,255,0.1) 0%, transparent 30%);
  opacity: 0.4;
}

.bg-gradient {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(145deg, #1a2f3f 0%, #162b3a 100%);
}

/* Layout */
.resume-layout {
  display: flex;
  min-height: 100vh;
  position: relative;
  z-index: 1;
}

/* Sidebar */
.sidebar {
  width: 280px;
  background: rgba(26, 32, 44, 0.95);
  backdrop-filter: blur(10px);
  border-right: 1px solid rgba(255, 255, 255, 0.1);
  display: flex;
  flex-direction: column;
  transition: all 0.3s ease;
  position: fixed;
  height: 100vh;
  z-index: 100;
}

.sidebar-collapsed {
  width: 80px;
}

.sidebar-header {
  padding: 24px 16px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  border-bottom: 1px solid rgba(255, 255, 255, 0.1);
}

.profile-mini {
  display: flex;
  align-items: center;
  gap: 12px;
  overflow: hidden;
}

.profile-mini-avatar {
  border: 2px solid #667eea;
  flex-shrink: 0;
}

.profile-mini-info h3 {
  margin: 0;
  font-size: 16px;
  color: white;
  font-weight: 600;
}

.profile-mini-info p {
  margin: 4px 0 0;
  font-size: 12px;
  color: rgba(255, 255, 255, 0.6);
}

.sidebar-toggle {
  color: white !important;
}

.sidebar-menu {
  flex: 1;
  background: transparent !important;
  border: none !important;
  padding: 16px 0;
}

.sidebar-menu :deep(.el-menu-item) {
  color: rgba(255, 255, 255, 0.7);
  margin: 4px 8px;
  border-radius: 8px;
}

.sidebar-menu :deep(.el-menu-item.is-active) {
  background: linear-gradient(90deg, #667eea, #764ba2) !important;
  color: white !important;
}

.sidebar-menu :deep(.el-menu-item:hover) {
  background: rgba(255, 255, 255, 0.1) !important;
  color: white !important;
}

.sidebar-menu :deep(.el-menu-item .el-icon) {
  color: currentColor;
}

.sidebar-footer {
  padding: 24px 16px;
  border-top: 1px solid rgba(255, 255, 255, 0.1);
}

.availability-badge {
  display: flex;
  align-items: center;
  gap: 8px;
  padding: 8px 12px;
  background: rgba(102, 126, 234, 0.2);
  border-radius: 20px;
  margin-bottom: 16px;
  color: rgba(255, 255, 255, 0.8);
  font-size: 13px;
}

.status-dot {
  width: 8px;
  height: 8px;
  background: #67c23a;
  border-radius: 50%;
  display: inline-block;
  animation: pulse 2s infinite;
}

.sidebar-contact {
  display: flex;
  gap: 8px;
  justify-content: center;
}

.sidebar-contact .el-button {
  background: rgba(255, 255, 255, 0.1) !important;
  border-color: transparent !important;
  color: white !important;
}

.sidebar-contact .el-button:hover {
  background: #667eea !important;
}

/* Main Content */
.main-content {
  flex: 1;
  margin-left: 280px;
  padding: 40px;
  transition: all 0.3s ease;
}

.sidebar-collapsed + .main-content {
  margin-left: 80px;
}

/* Hero Banner */
.hero-banner {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  border-radius: 20px;
  padding: 48px;
  margin-bottom: 48px;
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
  position: relative;
  overflow: hidden;
}

.hero-banner::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100" opacity="0.1"><path d="M0 0 L100 100 M100 0 L0 100" stroke="white" stroke-width="1"/></svg>');
  opacity: 0.1;
}

.hero-greeting {
  background: rgba(255, 255, 255, 0.2) !important;
  border: 1px solid rgba(255, 255, 255, 0.3) !important;
  color: white !important;
  margin-bottom: 24px;
}

.hero-text h1 {
  font-size: 48px;
  font-weight: 800;
  color: white;
  margin: 0 0 8px;
  line-height: 1.2;
}

.hero-text h2 {
  font-size: 24px;
  font-weight: 500;
  color: rgba(255, 255, 255, 0.9);
  margin: 0 0 16px;
}

.hero-bio {
  font-size: 16px;
  line-height: 1.8;
  color: rgba(255, 255, 255, 0.8);
  margin-bottom: 32px;
  max-width: 600px;
}

.hero-actions {
  display: flex;
  gap: 16px;
}

.hero-actions .el-button--primary {
  background: white;
  color: #667eea;
  border: none;
}

.hero-actions .el-button--default {
  background: rgba(255, 255, 255, 0.2);
  border: 1px solid rgba(255, 255, 255, 0.3);
  color: white;
}

.hero-stats-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 16px;
}

.stat-card {
  background: rgba(255, 255, 255, 0.1);
  backdrop-filter: blur(10px);
  border-radius: 12px;
  padding: 24px 16px;
  text-align: center;
  border: 1px solid rgba(255, 255, 255, 0.2);
}

.stat-number {
  display: block;
  font-size: 32px;
  font-weight: 800;
  color: white;
  line-height: 1.2;
}

.stat-label {
  font-size: 14px;
  color: rgba(255, 255, 255, 0.8);
}

/* Content Sections */
.content-section {
  margin-bottom: 64px;
}

.section-header {
  margin-bottom: 24px;
}

.section-header h3 {
  font-size: 28px;
  font-weight: 600;
  color: #2c3e50;
  margin: 0 0 8px;
}

.section-header .el-divider {
  margin: 0;
  width: 60px;
  height: 4px;
  background: linear-gradient(90deg, #667eea, #764ba2);
  border: none;
}

/* Cards */
.summary-card,
.contact-card,
.skill-category-card,
.experience-card,
.education-card,
.project-card,
.achievement-card {
  background: white !important;
  border: none !important;
  border-radius: 12px !important;
}

.summary-text {
  font-size: 16px;
  line-height: 1.8;
  color: #4a5568;
  margin-bottom: 24px;
}

.summary-highlights {
  display: flex;
  gap: 12px;
  flex-wrap: wrap;
}

.summary-highlights .el-tag {
  background: #f7f9fc !important;
  border-color: #e2e8f0 !important;
  color: #4a5568 !important;
}

.contact-item {
  display: flex;
  align-items: center;
  gap: 12px;
  padding: 12px 0;
  border-bottom: 1px solid #edf2f7;
}

.contact-item:last-child {
  border-bottom: none;
}

.contact-item .el-icon {
  color: #667eea;
  font-size: 18px;
}

.contact-item a {
  color: #4a5568;
  text-decoration: none;
}

.contact-item a:hover {
  color: #667eea;
}

/* Skill Categories */
.skill-category-header {
  display: flex;
  align-items: center;
  gap: 12px;
}

.skill-category-header .el-icon {
  font-size: 24px;
  color: #667eea;
}

.skill-category-header span {
  font-size: 16px;
  font-weight: 600;
  color: #2d3748;
}

.skill-items {
  padding: 8px 0;
}

.skill-item {
  margin-bottom: 16px;
}

.skill-info {
  display: flex;
  justify-content: space-between;
  margin-bottom: 4px;
  color: #4a5568;
  font-size: 14px;
}

.skill-level {
  color: #667eea;
  font-weight: 600;
}

/* Experience Timeline */
.experience-card {
  padding: 16px;
}

.experience-card h4 {
  margin: 0 0 8px;
  font-size: 18px;
  color: #2d3748;
}

.exp-company {
  color: #667eea;
  font-size: 14px;
  margin-bottom: 12px;
  font-weight: 500;
}

.exp-description {
  margin: 0;
  padding-left: 20px;
  color: #4a5568;
}

.exp-description li {
  margin-bottom: 8px;
  line-height: 1.6;
}

/* Education Timeline */
.education-timeline {
  position: relative;
  padding-left: 30px;
}

.education-timeline::before {
  content: '';
  position: absolute;
  left: 0;
  top: 0;
  bottom: 0;
  width: 2px;
  background: linear-gradient(180deg, #667eea, #764ba2);
}

.edu-item {
  position: relative;
  margin-bottom: 24px;
}

.edu-marker {
  position: absolute;
  left: -38px;
  top: 20px;
  width: 16px;
  height: 16px;
  border-radius: 50%;
  background: #cbd5e0;
  border: 3px solid white;
  z-index: 2;
}

.edu-marker.active {
  background: #667eea;
  box-shadow: 0 0 0 3px rgba(102, 126, 234, 0.2);
}

.education-card {
  padding: 16px;
}

.edu-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 8px;
}

.edu-header h4 {
  margin: 0;
  font-size: 18px;
  color: #2d3748;
}

.edu-institution {
  color: #667eea;
  font-size: 14px;
  margin-bottom: 4px;
}

.edu-period {
  color: #718096;
  font-size: 13px;
  margin-bottom: 8px;
}

.edu-research {
  display: flex;
  align-items: center;
  gap: 8px;
  color: #4a5568;
  font-size: 14px;
  margin: 8px 0 0;
  padding-top: 8px;
  border-top: 1px dashed #e2e8f0;
}

/* Projects */
.project-tabs {
  margin-bottom: 24px;
}

.project-tabs :deep(.el-tabs__item) {
  font-size: 16px;
  padding: 0 24px;
}

.project-card {
  overflow: hidden;
  transition: transform 0.3s;
}

.project-card:hover {
  transform: translateY(-4px);
}

.project-image {
  height: 200px;
  position: relative;
  overflow: hidden;
}

.project-image .el-image {
  width: 100%;
  height: 100%;
}

.image-error {
  width: 100%;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  background: #f7f9fc;
  color: #cbd5e0;
}

.project-badge {
  position: absolute;
  top: 16px;
  right: 16px;
  background: #f56c6c;
  color: white;
  padding: 4px 12px;
  border-radius: 20px;
  font-size: 12px;
  font-weight: 500;
}

.project-content {
  padding: 20px;
}

.project-content h4 {
  margin: 0 0 8px;
  font-size: 18px;
  color: #2d3748;
}

.project-content p {
  color: #718096;
  font-size: 14px;
  line-height: 1.6;
  margin-bottom: 16px;
}

.project-tech {
  display: flex;
  gap: 8px;
  flex-wrap: wrap;
  margin-bottom: 16px;
}

.project-tech .el-tag {
  background: #f7f9fc !important;
  border-color: #e2e8f0 !important;
  color: #4a5568 !important;
}

.project-link {
  padding: 0;
}

/* Achievements */
.achievement-card {
  text-align: center;
  padding: 32px 24px !important;
}

.achievement-icon {
  font-size: 48px;
  color: #667eea;
  margin-bottom: 16px;
}

.achievement-card h4 {
  margin: 0 0 12px;
  font-size: 20px;
  color: #2d3748;
}

.achievement-card p {
  color: #718096;
  font-size: 14px;
  line-height: 1.6;
  margin-bottom: 16px;
}

/* CTA Section */
.cta-card {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%) !important;
  border: none !important;
  padding: 32px !important;
}

.cta-card h3 {
  font-size: 24px;
  font-weight: 600;
  color: white;
  margin: 0 0 8px;
}

.cta-card p {
  color: rgba(255, 255, 255, 0.9);
  font-size: 16px;
  margin: 0;
}

.cta-actions {
  display: flex;
  gap: 16px;
  justify-content: flex-end;
}

.cta-actions .el-button--primary {
  background: white;
  color: #667eea;
  border: none;
}

.cta-actions .el-button--default {
  background: rgba(255, 255, 255, 0.2);
  border: 1px solid rgba(255, 255, 255, 0.3);
  color: white;
}

/* Animations */
@keyframes pulse {
  0%, 100% {
    opacity: 1;
  }
  50% {
    opacity: 0.5;
  }
}

/* Responsive */
@media (max-width: 1024px) {
  .sidebar {
    width: 240px;
  }
  
  .main-content {
    margin-left: 240px;
    padding: 24px;
  }
  
  .hero-text h1 {
    font-size: 36px;
  }
  
  .hero-text h2 {
    font-size: 20px;
  }
}

@media (max-width: 768px) {
  .sidebar {
    transform: translateX(-100%);
  }
  
  .sidebar.sidebar-collapsed {
    transform: translateX(0);
    width: 80px;
  }
  
  .main-content {
    margin-left: 0;
  }
  
  .hero-banner {
    padding: 32px 20px;
  }
  
  .hero-stats-grid {
    margin-top: 24px;
  }
  
  .cta-actions {
    margin-top: 16px;
    justify-content: flex-start;
  }
}
</style>