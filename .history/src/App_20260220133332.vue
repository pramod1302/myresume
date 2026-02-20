<template>
  <div class="enterprise-resume">
    <!-- Premium Background System -->
    <div class="background-system">
      <div class="gradient-mesh"></div>
      <div class="noise-overlay"></div>
      <div class="floating-particles">
        <div v-for="n in 50" :key="n" class="particle" :style="getParticleStyle(n)"></div>
      </div>
    </div>

    <!-- Main Layout -->
    <div class="resume-grid">
      <!-- Sticky Sidebar -->
      <aside class="resume-sidebar">
        <div class="sidebar-sticky">
          <!-- Profile Section -->
          <div class="profile-section">
            <div class="avatar-wrapper">
              <el-avatar :size="140" class="profile-avatar">
                <img src="./1000005132.jpg" alt="Pramod N" @error="handleImageError">
              </el-avatar>
              <div class="avatar-ring"></div>
            </div>
            <h1 class="profile-name">Pramod N</h1>
            <p class="profile-title">Assistant Professor & Full Stack Developer</p>
            
            <div class="availability-indicator">
              <span class="status-dot pulse"></span>
              <span>Available for opportunities</span>
            </div>

            <!-- Quick Stats -->
            <div class="quick-stats">
              <div class="stat">
                <span class="stat-value">5+</span>
                <span class="stat-label">Projects</span>
              </div>
              <div class="stat-divider"></div>
              <div class="stat">
                <span class="stat-value">3</span>
                <span class="stat-label">Languages</span>
              </div>
              <div class="stat-divider"></div>
              <div class="stat">
                <span class="stat-value">2+</span>
                <span class="stat-label">Years</span>
              </div>
            </div>
          </div>

          <!-- Navigation Menu -->
          <el-menu
            :default-active="activeSection"
            class="profile-menu"
            :collapse="false"
            @select="handleMenuSelect"
            background-color="transparent"
            text-color="#a0aec0"
            active-text-color="#4299e1"
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
            <el-menu-item index="publications">
              <el-icon><Document /></el-icon>
              <span>Publications</span>
            </el-menu-item>
          </el-menu>

          <!-- Contact Information -->
          <div class="contact-info">
            <h3 class="sidebar-heading">Contact</h3>
            <div class="contact-item" @click="copyToClipboard('+91 8861326592')">
              <el-icon><Phone /></el-icon>
              <span>+91 8861326592</span>
            </div>
            <div class="contact-item" @click="copyToClipboard('pramod.n1301@gmail.com')">
              <el-icon><Message /></el-icon>
              <span>pramod.n1301@gmail.com</span>
            </div>
            <div class="contact-item">
              <el-icon><Location /></el-icon>
              <span>Bangalore, KA</span>
            </div>
            <div class="contact-item">
              <el-icon><Link /></el-icon>
              <a href="https://linkedin.com/in/pramod-n-a965b9264/" target="_blank">linkedin.com/in/pramod-n</a>
            </div>
          </div>

          <!-- Download Resume -->
          <el-button type="primary" class="download-btn" :icon="Download" @click="downloadResume" long>
            Download Resume
          </el-button>
        </div>
      </aside>

      <!-- Main Content -->
      <main class="resume-main">
        <!-- Hero Section -->
        <section class="hero-section" ref="hero">
          <div class="hero-content">
            <div class="hero-text">
              <el-tag class="hero-badge" size="large" effect="dark">Ph.D. Candidate · IoT & Blockchain</el-tag>
              <h1 class="hero-greeting">Hello, I'm <span class="highlight">Pramod</span></h1>
              <p class="hero-description">
                Bridging the gap between academic excellence and practical innovation. 
                With a passion for teaching and development, I create solutions that matter.
              </p>
              <div class="hero-cta">
                <el-button type="primary" size="large" @click="scrollToSection('projects')">
                  View My Work
                  <el-icon><ArrowRight /></el-icon>
                </el-button>
                <el-button size="large" @click="scrollToSection('contact')">
                  Let's Connect
                </el-button>
              </div>
            </div>
            <div class="hero-visual">
              <div class="code-snippet">
                <pre><code>{
  "name": "Pramod N",
  "role": "Assistant Professor",
  "expertise": [
    "Full Stack Development",
    "IoT Architecture",
    "Blockchain"
  ],
  "current": "Ph.D. Candidate",
  "passion": "Mentoring & Innovation"
}</code></pre>
              </div>
            </div>
          </div>
        </section>

        <!-- Summary Section -->
        <section id="summary" class="content-section" ref="summary">
          <div class="section-header">
            <el-icon class="section-icon"><Document /></el-icon>
            <h2>Professional Summary</h2>
          </div>
          
          <el-row :gutter="24">
            <el-col :span="16">
              <el-card class="summary-card" shadow="hover">
                <p class="summary-text">
                  Motivated academic and developer with experience as an Assistant Professor 
                  and a strong foundation in computer applications. Passionate about teaching, 
                  research, and contributing to innovative projects. Currently pursuing Ph.D. 
                  in IoT with Blockchain, aiming to bridge theoretical research with practical 
                  applications.
                </p>
                <div class="key-highlights">
                  <div v-for="item in highlights" :key="item" class="highlight-item">
                    <el-icon><Check /></el-icon>
                    <span>{{ item }}</span>
                  </div>
                </div>
              </el-card>
            </el-col>
            <el-col :span="8">
              <el-card class="expertise-card" shadow="hover">
                <h3>Core Competencies</h3>
                <div class="competency-list">
                  <div v-for="comp in competencies" :key="comp.name" class="competency-item">
                    <span class="competency-name">{{ comp.name }}</span>
                    <el-rate v-model="comp.level" disabled :colors="['#4299e1', '#4299e1', '#4299e1']" />
                  </div>
                </div>
              </el-card>
            </el-col>
          </el-row>
        </section>

        <!-- Skills Section -->
        <section id="skills" class="content-section" ref="skills">
          <div class="section-header">
            <el-icon class="section-icon"><Monitor /></el-icon>
            <h2>Technical Expertise</h2>
          </div>

          <el-row :gutter="24">
            <el-col :span="8" v-for="category in skillCategories" :key="category.title">
              <el-card class="skill-card" shadow="hover">
                <template #header>
                  <div class="skill-card-header">
                    <el-icon><component :is="category.icon" /></el-icon>
                    <h3>{{ category.title }}</h3>
                  </div>
                </template>
                <div class="skill-list">
                  <div v-for="skill in category.skills" :key="skill.name" class="skill-item">
                    <div class="skill-info">
                      <span>{{ skill.name }}</span>
                      <span class="skill-percentage">{{ skill.level }}%</span>
                    </div>
                    <div class="skill-bar">
                      <div class="skill-progress" :style="{ width: skill.level + '%' }"></div>
                    </div>
                  </div>
                </div>
              </el-card>
            </el-col>
          </el-row>
        </section>

        <!-- Experience & Education -->
        <section id="experience" class="content-section" ref="experience">
          <el-row :gutter="24">
            <el-col :span="12">
              <div class="section-header">
                <el-icon class="section-icon"><Briefcase /></el-icon>
                <h2>Work Experience</h2>
              </div>
              
              <div class="timeline">
                <div v-for="(exp, index) in experiences" :key="index" class="timeline-item">
                  <div class="timeline-marker" :class="{ 'active': index === 0 }"></div>
                  <el-card class="timeline-card" shadow="hover">
                    <div class="timeline-header">
                      <h3>{{ exp.title }}</h3>
                      <el-tag size="small" :type="index === 0 ? 'danger' : 'info'">
                        {{ exp.period }}
                      </el-tag>
                    </div>
                    <p class="timeline-subtitle">{{ exp.company }}</p>
                    <ul class="timeline-description">
                      <li v-for="item in exp.description" :key="item">{{ item }}</li>
                    </ul>
                  </el-card>
                </div>
              </div>
            </el-col>

            <el-col :span="12">
              <div class="section-header">
                <el-icon class="section-icon"><Reading /></el-icon>
                <h2>Education</h2>
              </div>

              <div class="education-grid">
                <el-card v-for="(edu, index) in education" :key="index" class="education-card" shadow="hover">
                  <div class="education-header">
                    <div class="education-icon">
                      <el-icon><School /></el-icon>
                    </div>
                    <div class="education-title">
                      <h3>{{ edu.degree }}</h3>
                      <p>{{ edu.institution }}</p>
                    </div>
                  </div>
                  <div class="education-meta">
                    <el-tag size="small" :type="index === 0 ? 'danger' : 'info'">
                      {{ edu.period }}
                    </el-tag>
                    <el-tag size="small" effect="plain">{{ edu.score }}</el-tag>
                  </div>
                  <p v-if="edu.research" class="education-research">
                    <el-icon><Microscope /></el-icon>
                    {{ edu.research }}
                  </p>
                </el-card>
              </div>
            </el-col>
          </el-row>
        </section>

        <!-- Projects Section -->
        <section id="projects" class="content-section" ref="projects">
          <div class="section-header">
            <el-icon class="section-icon"><DataBoard /></el-icon>
            <h2>Featured Projects</h2>
            <div class="view-toggle">
              <el-radio-group v-model="projectView" size="small">
                <el-radio-button label="grid">
                  <el-icon><Grid /></el-icon>
                </el-radio-button>
                <el-radio-button label="list">
                  <el-icon><List /></el-icon>
                </el-radio-button>
              </el-radio-group>
            </div>
          </div>

          <!-- Grid View -->
          <el-row :gutter="24" v-if="projectView === 'grid'">
            <el-col :xs="24" :sm="12" :lg="8" v-for="project in projects" :key="project.title">
              <el-card class="project-card" shadow="hover">
                <div class="project-image">
                  <img :src="project.image" :alt="project.title">
                  <div class="project-overlay">
                    <el-tag v-if="project.badge" class="project-badge" type="danger">{{ project.badge }}</el-tag>
                  </div>
                </div>
                <div class="project-content">
                  <h3>{{ project.title }}</h3>
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
                    View Details
                    <el-icon><ArrowRight /></el-icon>
                  </el-button>
                </div>
              </el-card>
            </el-col>
          </el-row>

          <!-- List View -->
          <el-table v-else :data="projects" style="width: 100%" stripe>
            <el-table-column prop="title" label="Project" width="200" />
            <el-table-column prop="description" label="Description" />
            <el-table-column label="Tech Stack" width="300">
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
            <el-table-column label="Badge" width="120">
              <template #default="{ row }">
                <el-tag v-if="row.badge" type="danger" size="small">{{ row.badge }}</el-tag>
              </template>
            </el-table-column>
          </el-table>
        </section>

        <!-- Publications Section -->
        <section id="publications" class="content-section" ref="publications">
          <div class="section-header">
            <el-icon class="section-icon"><Document /></el-icon>
            <h2>Research & Publications</h2>
          </div>

          <el-row :gutter="24">
            <el-col :span="12" v-for="pub in publications" :key="pub.title">
              <el-card class="publication-card" shadow="hover">
                <div class="publication-type">{{ pub.type }}</div>
                <h3>{{ pub.title }}</h3>
                <p class="publication-authors">{{ pub.authors }}</p>
                <p class="publication-venue">{{ pub.venue }} · {{ pub.year }}</p>
                <div class="publication-links">
                  <el-button text type="primary" size="small">
                    <el-icon><Link /></el-icon>
                    DOI
                  </el-button>
                  <el-button text type="primary" size="small">
                    <el-icon><Download /></el-icon>
                    PDF
                  </el-button>
                </div>
              </el-card>
            </el-col>
          </el-row>
        </section>

        <!-- Languages & Interests -->
        <section class="content-section">
          <el-row :gutter="24">
            <el-col :span="12">
              <el-card class="languages-card" shadow="hover">
                <template #header>
                  <div class="card-header">
                    <el-icon><Collection /></el-icon>
                    <h3>Languages</h3>
                  </div>
                </template>
                <div class="language-list">
                  <div v-for="lang in languages" :key="lang.name" class="language-item">
                    <span class="language-name">{{ lang.name }}</span>
                    <div class="language-level">
                      <div class="level-bar" :style="{ width: lang.level + '%' }"></div>
                    </div>
                    <span class="language-percentage">{{ lang.level }}%</span>
                  </div>
                </div>
              </el-card>
            </el-col>

            <el-col :span="12">
              <el-card class="interests-card" shadow="hover">
                <template #header>
                  <div class="card-header">
                    <el-icon><Star /></el-icon>
                    <h3>Interests & Passions</h3>
                  </div>
                </template>
                <div class="interests-grid">
                  <div v-for="interest in interests" :key="interest.name" class="interest-item">
                    <el-icon><component :is="interest.icon" /></el-icon>
                    <span>{{ interest.name }}</span>
                  </div>
                </div>
              </el-card>
            </el-col>
          </el-row>
        </section>
      </main>
    </div>

    <!-- Back to Top -->
    <el-backtop :right="30" :bottom="30" />
  </div>
</template>

<script>
import { ref } from 'vue'
import { 
  Document, Monitor, Briefcase, Reading, DataBoard, 
  Trophy, Message, Link, Download, ArrowRight, Phone,
  Location, Picture, Microscope, Expand, Fold,
  Star, Medal, Grid, List, Check, School,
  Coffee, Headset, Camera, Plane
} from '@element-plus/icons-vue'
import { ElMessage } from 'element-plus'

export default {
  name: 'EnterpriseResume',
  components: {
    Document, Monitor, Briefcase, Reading, DataBoard,
    Trophy, Message, Link, Download, ArrowRight, Phone,
    Location, Picture, Microscope, Expand, Fold,
    Star, Medal, Grid, List, Check, School,
    Coffee, Headset, Camera, Plane
  },
  setup() {
        const education = [
          {
            degree: 'Ph.D. in Computer Science',
            institution: 'Nitte Meenakshi Institute of Technology',
            period: '2025 - Present',
            score: 'Ongoing',
            research: 'Internet of Things (IoT) with Blockchain Integration'
          },
          {
            degree: 'Master of Computer Applications',
            institution: 'BMS Institute of Technology, Bengaluru',
            period: '2022 - 2024',
            score: 'CGPA: 7.4/10'
          },
          {
            degree: 'Bachelor of Science',
            institution: 'MES Degree College, Bengaluru',
            period: '2019 - 2022',
            score: 'CGPA: 7.4/10'
          },
          {
            degree: 'PUC (12th)',
            institution: 'St. Claret PU College, Bengaluru',
            period: '2017 - 2019',
            score: '65%'
          },
          {
            degree: 'SSLC (10th)',
            institution: 'Ideal English High School, Bengaluru',
            period: '2017',
            score: '87%'
          }
        ]

        const projects = [
          {
            title: 'Smart Doctor',
            tech: ['Java', 'Android', 'Firebase', 'SQL'],
            description: 'Healthcare mobile application providing smart diagnosis and doctor consultation support',
            badge: 'KSCST Shortlisted',
            image: 'https://images.unsplash.com/photo-1576091160399-112ba8d25d1d?w=400'
          },
          {
            title: 'Driver Drowsiness Alert',
            tech: ['Python', 'OpenCV', 'Machine Learning'],
            description: 'Computer vision–based system to detect driver fatigue and alert in real-time',
            image: 'https://images.unsplash.com/photo-1549317661-bd32c8ce0db2?w=400'
          },
          {
            title: 'Video Conference Application',
            tech: ['Node.js', 'Express.js', 'Firebase', 'WebRTC'],
            description: 'Cross-platform video conferencing app with real-time chat and secure authentication',
            image: 'https://images.unsplash.com/photo-1516387938699-a93567ec168e?w=400'
          },
          {
            title: 'AQI Analysis App',
            tech: ['Python', 'Firebase', 'REST APIs', 'Android'],
            description: 'Fetch and analyze Air Quality Index data with user-friendly dashboard',
            image: 'https://images.unsplash.com/photo-1584267385494-9fdd9a71ad75?w=400'
          },
          {
            title: 'E-Library Management',
            tech: ['Node.js', 'Express.js', 'Firebase', 'SQL'],
            description: 'Digital library system enabling book management, student access, and admin controls',
            image: 'https://images.unsplash.com/photo-1524995997946-a1c2e315a42f?w=400'
          }
        ]
    const activeSection = ref('summary')
    const projectView = ref('grid')
    
    // Section refs for scrolling
    const summary = ref(null)
    const skills = ref(null)
    const experience = ref(null)

    const highlights = [
      'Academic teaching experience',
      'Full Stack Development',
      'Research in IoT & Blockchain',
      'Project mentorship',
      'KSCST recognized project'
    ]

    const competencies = [
      { name: 'Teaching', level: 4.5 },
      { name: 'Development', level: 4 },
      { name: 'Research', level: 3.5 },
      { name: 'Mentoring', level: 4 }
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
        title: 'Frameworks',
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
          { name: 'Docker', level: 60 },
          { name: 'AWS', level: 55 }
        ]
      }
    ]

    const experiences = [
      {
        title: 'Assistant Professor',
        company: 'Department of MCA, Nitte Meenakshi Institute of Technology',
        period: '2024 - 2025',
        description: [
          'Taught core MCA subjects including programming, data structures, and project development',
          'Mentored postgraduate students on research-oriented academic projects',
          'Participated in academic reviews and curriculum planning meetings',
          'Coordinated technical workshops and departmental hackathons'
        ]
      }
    ]

    // ...existing code...

    const publications = [
      {
        type: 'Conference Paper',
        title: 'Blockchain-Integrated IoT Architecture for Healthcare Applications',
        authors: 'Pramod N, Dr. Smitha GR',
        venue: 'International Conference on Emerging Technologies',
        year: '2024'
      },
      {
        type: 'Journal Article',
        title: 'Review of Machine Learning Techniques in Driver Drowsiness Detection',
        authors: 'Pramod N, Dr. Kumar R',
        venue: 'Journal of Artificial Intelligence Research',
        year: '2023'
      }
    ]

    const languages = [
      { name: 'Kannada', level: 100 },
      { name: 'Hindi', level: 85 },
      { name: 'English', level: 80 }
    ]

    const interests = [
      { name: 'Travel', icon: 'Plane' },
      { name: 'Photography', icon: 'Camera' },
      { name: 'Swimming', icon: 'Headset' },
      { name: 'Reading', icon: 'Document' }
    ]

    const handleMenuSelect = (index) => {
      activeSection.value = index
      scrollToSection(index)
    }

    const scrollToSection = (section) => {
      const element = document.getElementById(section)
      if (element) {
        element.scrollIntoView({ behavior: 'smooth', block: 'start' })
      }
    }

    const handleImageError = (e) => {
      e.target.src = 'https://via.placeholder.com/140x140?text=PN'
    }

    const copyToClipboard = (text) => {
      navigator.clipboard.writeText(text)
      ElMessage.success('Copied to clipboard!')
    }

    const downloadResume = () => {
      ElMessage.success('Resume download started')
    }

    const getParticleStyle = () => {
      return {
        left: `${Math.random() * 100}%`,
        top: `${Math.random() * 100}%`,
        animationDelay: `${Math.random() * 5}s`,
        width: `${Math.random() * 3 + 1}px`,
        height: `${Math.random() * 3 + 1}px`
      }
    }

    return {
      activeSection,
      projectView,
      summary,
      skills,
      experience,
      education,
      projects,
      publications,
      highlights,
      competencies,
      skillCategories,
      experiences,
      languages,
      interests,
      handleMenuSelect,
      scrollToSection,
      handleImageError,
      copyToClipboard,
      downloadResume,
      getParticleStyle,
      Document,
      Monitor,
      Briefcase,
      Reading,
      DataBoard,
      Download,
      ArrowRight,
      Phone,
      Message,
      Location,
      Link,
      Check,
      School,
      Microscope,
      Grid,
      List,
      Star,
      Camera,
      Plane,
      Headset
    }
  }
}
</script>

<style scoped>
.enterprise-resume {
  min-height: 100vh;
  background: #0a192f;
  position: relative;
  font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
  color: #e6f1ff;
}

/* Background System */
.background-system {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: 0;
}

.gradient-mesh {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: 
    radial-gradient(circle at 20% 30%, rgba(66, 153, 225, 0.15) 0%, transparent 30%),
    radial-gradient(circle at 80% 70%, rgba(100, 255, 218, 0.1) 0%, transparent 35%),
    linear-gradient(135deg, #0a192f 0%, #112240 100%);
}

.noise-overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-image: url('data:image/svg+xml,<svg viewBox="0 0 200 200" xmlns="http://www.w3.org/2000/svg"><filter id="noise"><feTurbulence type="fractalNoise" baseFrequency="0.65" numOctaves="3" stitchTiles="stitch"/></filter><rect width="100%" height="100%" filter="url(%23noise)" opacity="0.08"/></svg>');
  opacity: 0.4;
  pointer-events: none;
}

.floating-particles {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  pointer-events: none;
}

.particle {
  position: absolute;
  background: rgba(100, 255, 218, 0.3);
  border-radius: 50%;
  animation: float-particle 8s infinite ease-in-out;
}

@keyframes float-particle {
  0%, 100% { transform: translate(0, 0); }
  50% { transform: translate(10px, -10px); }
}

/* Resume Grid Layout */
.resume-grid {
  display: grid;
  grid-template-columns: 320px 1fr;
  min-height: 100vh;
  position: relative;
  z-index: 1;
}

/* Sidebar */
.resume-sidebar {
  background: rgba(17, 34, 64, 0.95);
  backdrop-filter: blur(10px);
  border-right: 1px solid rgba(100, 255, 218, 0.1);
  position: relative;
}

.sidebar-sticky {
  position: sticky;
  top: 0;
  padding: 40px 24px;
  height: 100vh;
  overflow-y: auto;
  scrollbar-width: thin;
  scrollbar-color: #4299e1 #1e3a5f;
}

.sidebar-sticky::-webkit-scrollbar {
  width: 4px;
}

.sidebar-sticky::-webkit-scrollbar-track {
  background: #1e3a5f;
}

.sidebar-sticky::-webkit-scrollbar-thumb {
  background: #4299e1;
  border-radius: 4px;
}

/* Profile Section */
.profile-section {
  text-align: center;
  margin-bottom: 32px;
}

.avatar-wrapper {
  position: relative;
  width: fit-content;
  margin: 0 auto 20px;
}

.profile-avatar {
  border: 3px solid #4299e1;
  box-shadow: 0 10px 30px -10px rgba(66, 153, 225, 0.5);
  position: relative;
  z-index: 2;
}

.avatar-ring {
  position: absolute;
  top: -5px;
  left: -5px;
  right: -5px;
  bottom: -5px;
  border: 2px solid rgba(100, 255, 218, 0.3);
  border-radius: 50%;
  animation: rotate-ring 10s linear infinite;
}

@keyframes rotate-ring {
  from { transform: rotate(0deg); }
  to { transform: rotate(360deg); }
}

.profile-name {
  font-size: 24px;
  font-weight: 700;
  color: #e6f1ff;
  margin: 0 0 4px;
}

.profile-title {
  font-size: 14px;
  color: #64ffda;
  margin-bottom: 16px;
}

.availability-indicator {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 8px;
  font-size: 13px;
  color: #a0aec0;
  margin-bottom: 24px;
}

.status-dot {
  width: 8px;
  height: 8px;
  background: #48bb78;
  border-radius: 50%;
}

.pulse {
  animation: pulse 2s infinite;
}

@keyframes pulse {
  0%, 100% { opacity: 1; }
  50% { opacity: 0.5; }
}

/* Quick Stats */
.quick-stats {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 16px;
  padding: 16px;
  background: rgba(10, 25, 47, 0.5);
  border-radius: 12px;
  border: 1px solid rgba(100, 255, 218, 0.1);
}

.stat {
  text-align: center;
}

.stat-value {
  display: block;
  font-size: 20px;
  font-weight: 700;
  color: #64ffda;
}

.stat-label {
  font-size: 12px;
  color: #a0aec0;
}

.stat-divider {
  width: 1px;
  height: 30px;
  background: rgba(100, 255, 218, 0.2);
}

/* Profile Menu */
.profile-menu {
  margin-bottom: 32px;
  border: none !important;
}

.profile-menu :deep(.el-menu-item) {
  height: 48px;
  line-height: 48px;
  border-radius: 8px;
  margin: 4px 0;
}

.profile-menu :deep(.el-menu-item.is-active) {
  background: linear-gradient(90deg, rgba(66, 153, 225, 0.2), transparent) !important;
  color: #4299e1 !important;
}

.profile-menu :deep(.el-menu-item:hover) {
  background: rgba(66, 153, 225, 0.1) !important;
  color: #64ffda !important;
}

/* Contact Info */
.contact-info {
  margin-bottom: 32px;
}

.sidebar-heading {
  font-size: 16px;
  font-weight: 600;
  color: #e6f1ff;
  margin-bottom: 16px;
  letter-spacing: 0.5px;
}

.contact-item {
  display: flex;
  align-items: center;
  gap: 12px;
  padding: 12px;
  border-radius: 8px;
  cursor: pointer;
  transition: all 0.3s;
  color: #a0aec0;
}

.contact-item:hover {
  background: rgba(66, 153, 225, 0.1);
  color: #64ffda;
}

.contact-item .el-icon {
  font-size: 18px;
  color: #4299e1;
}

.contact-item a {
  color: inherit;
  text-decoration: none;
}

/* Download Button */
.download-btn {
  width: 100%;
  background: linear-gradient(90deg, #4299e1, #64ffda) !important;
  border: none !important;
  height: 48px;
  font-weight: 600;
  letter-spacing: 0.5px;
}

/* Main Content */
.resume-main {
  padding: 40px;
  max-width: 1200px;
}

/* Hero Section */
.hero-section {
  margin-bottom: 60px;
  padding: 40px;
  background: rgba(17, 34, 64, 0.5);
  backdrop-filter: blur(10px);
  border-radius: 24px;
  border: 1px solid rgba(100, 255, 218, 0.1);
}

.hero-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 40px;
  align-items: center;
}

.hero-badge {
  background: rgba(66, 153, 225, 0.2) !important;
  border: 1px solid #4299e1 !important;
  color: #64ffda !important;
  margin-bottom: 20px;
}

.hero-greeting {
  font-size: 48px;
  font-weight: 800;
  color: #e6f1ff;
  margin: 0 0 16px;
  line-height: 1.2;
}

.highlight {
  color: #64ffda;
  position: relative;
  display: inline-block;
}

.highlight::after {
  content: '';
  position: absolute;
  bottom: 5px;
  left: 0;
  width: 100%;
  height: 8px;
  background: rgba(100, 255, 218, 0.2);
  z-index: -1;
}

.hero-description {
  font-size: 16px;
  line-height: 1.8;
  color: #a0aec0;
  margin-bottom: 32px;
}

.hero-cta {
  display: flex;
  gap: 16px;
}

.hero-cta .el-button--primary {
  background: #4299e1;
  border: none;
}

.hero-cta .el-button--primary:hover {
  background: #64ffda;
  color: #0a192f;
}

.code-snippet {
  background: #0a192f;
  border-radius: 16px;
  padding: 24px;
  border: 1px solid rgba(100, 255, 218, 0.2);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.4);
}

.code-snippet pre {
  margin: 0;
  color: #64ffda;
  font-family: 'Fira Code', monospace;
  font-size: 14px;
}

.code-snippet code {
  color: #e6f1ff;
}

/* Content Sections */
.content-section {
  margin-bottom: 60px;
  scroll-margin-top: 40px;
}

.section-header {
  display: flex;
  align-items: center;
  gap: 12px;
  margin-bottom: 32px;
  position: relative;
}

.section-icon {
  font-size: 28px;
  color: #64ffda;
}

.section-header h2 {
  font-size: 28px;
  font-weight: 700;
  color: #e6f1ff;
  margin: 0;
}

.view-toggle {
  margin-left: auto;
}

.view-toggle .el-radio-group {
  background: rgba(17, 34, 64, 0.8);
  border: 1px solid rgba(100, 255, 218, 0.2);
  border-radius: 8px;
}

.view-toggle .el-radio-button__inner {
  background: transparent !important;
  border: none !important;
  color: #a0aec0;
}

.view-toggle .el-radio-button__original-radio:checked + .el-radio-button__inner {
  color: #64ffda !important;
  background: rgba(100, 255, 218, 0.1) !important;
}

/* Summary Card */
.summary-card {
  background: rgba(17, 34, 64, 0.8) !important;
  border: 1px solid rgba(100, 255, 218, 0.1) !important;
  backdrop-filter: blur(10px);
}

.summary-text {
  font-size: 16px;
  line-height: 1.8;
  color: #a0aec0;
  margin-bottom: 24px;
}

.key-highlights {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 12px;
}

.highlight-item {
  display: flex;
  align-items: center;
  gap: 8px;
  color: #e6f1ff;
  font-size: 14px;
}

.highlight-item .el-icon {
  color: #64ffda;
  font-size: 16px;
}

/* Expertise Card */
.expertise-card {
  background: rgba(17, 34, 64, 0.8) !important;
  border: 1px solid rgba(100, 255, 218, 0.1) !important;
  height: 100%;
}

.expertise-card h3 {
  color: #e6f1ff;
  margin: 0 0 16px;
  font-size: 18px;
}

.competency-item {
  margin-bottom: 16px;
}

.competency-name {
  display: block;
  color: #a0aec0;
  margin-bottom: 4px;
  font-size: 14px;
}

/* Skill Cards */
.skill-card {
  background: rgba(17, 34, 64, 0.8) !important;
  border: 1px solid rgba(100, 255, 218, 0.1) !important;
  margin-bottom: 24px;
}

.skill-card-header {
  display: flex;
  align-items: center;
  gap: 12px;
}

.skill-card-header .el-icon {
  font-size: 20px;
  color: #64ffda;
}

.skill-card-header h3 {
  margin: 0;
  font-size: 16px;
  color: #e6f1ff;
}

.skill-list {
  padding: 8px 0;
}

.skill-item {
  margin-bottom: 16px;
}

.skill-info {
  display: flex;
  justify-content: space-between;
  margin-bottom: 4px;
  color: #a0aec0;
  font-size: 14px;
}

.skill-percentage {
  color: #64ffda;
  font-weight: 600;
}

.skill-bar {
  height: 6px;
  background: rgba(255, 255, 255, 0.1);
  border-radius: 3px;
  overflow: hidden;
}

.skill-progress {
  height: 100%;
  background: linear-gradient(90deg, #4299e1, #64ffda);
  border-radius: 3px;
  transition: width 1s ease;
}

/* Timeline */
.timeline {
  position: relative;
  padding-left: 30px;
}

.timeline::before {
  content: '';
  position: absolute;
  left: 0;
  top: 0;
  bottom: 0;
  width: 2px;
  background: linear-gradient(180deg, #4299e1, #64ffda);
}

.timeline-item {
  position: relative;
  margin-bottom: 24px;
}

.timeline-marker {
  position: absolute;
  left: -38px;
  top: 24px;
  width: 16px;
  height: 16px;
  border-radius: 50%;
  background: #4299e1;
  border: 3px solid #0a192f;
  z-index: 2;
}

.timeline-marker.active {
  background: #64ffda;
  box-shadow: 0 0 0 3px rgba(100, 255, 218, 0.3);
}

.timeline-card {
  background: rgba(17, 34, 64, 0.8) !important;
  border: 1px solid rgba(100, 255, 218, 0.1) !important;
}

.timeline-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 8px;
}

.timeline-header h3 {
  margin: 0;
  font-size: 18px;
  color: #e6f1ff;
}

.timeline-subtitle {
  color: #64ffda;
  font-size: 14px;
  margin-bottom: 12px;
}

.timeline-description {
  margin: 0;
  padding-left: 20px;
  color: #a0aec0;
}

.timeline-description li {
  margin-bottom: 8px;
  line-height: 1.6;
}

/* Education Grid */
.education-grid {
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.education-card {
  background: rgba(17, 34, 64, 0.8) !important;
  border: 1px solid rgba(100, 255, 218, 0.1) !important;
}

.education-header {
  display: flex;
  gap: 16px;
  margin-bottom: 12px;
}

.education-icon {
  width: 40px;
  height: 40px;
  background: rgba(100, 255, 218, 0.1);
  border-radius: 8px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.education-icon .el-icon {
  font-size: 20px;
  color: #64ffda;
}

.education-title h3 {
  margin: 0 0 4px;
  font-size: 16px;
  color: #e6f1ff;
}

.education-title p {
  margin: 0;
  font-size: 14px;
  color: #a0aec0;
}

.education-meta {
  display: flex;
  gap: 8px;
  margin-bottom: 8px;
}

.education-research {
  display: flex;
  align-items: center;
  gap: 8px;
  color: #a0aec0;
  font-size: 13px;
  margin: 8px 0 0;
  padding-top: 8px;
  border-top: 1px solid rgba(100, 255, 218, 0.1);
}

/* Project Cards */
.project-card {
  background: rgba(17, 34, 64, 0.8) !important;
  border: 1px solid rgba(100, 255, 218, 0.1) !important;
  overflow: hidden;
  transition: transform 0.3s;
  margin-bottom: 24px;
}

.project-card:hover {
  transform: translateY(-4px);
}

.project-image {
  height: 200px;
  position: relative;
  overflow: hidden;
}

.project-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.3s;
}

.project-card:hover .project-image img {
  transform: scale(1.05);
}

.project-overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: linear-gradient(180deg, transparent 0%, rgba(10, 25, 47, 0.8) 100%);
}

.project-badge {
  position: absolute;
  top: 16px;
  right: 16px;
}

.project-content {
  padding: 20px;
}

.project-content h3 {
  margin: 0 0 8px;
  font-size: 18px;
  color: #e6f1ff;
}

.project-content p {
  color: #a0aec0;
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
  background: rgba(100, 255, 218, 0.1) !important;
  border-color: #64ffda !important;
  color: #64ffda !important;
}

.project-link {
  padding: 0;
  color: #4299e1;
}

/* Publication Cards */
.publication-card {
  background: rgba(17, 34, 64, 0.8) !important;
  border: 1px solid rgba(100, 255, 218, 0.1) !important;
  margin-bottom: 24px;
}

.publication-type {
  font-size: 12px;
  text-transform: uppercase;
  letter-spacing: 1px;
  color: #64ffda;
  margin-bottom: 8px;
}

.publication-card h3 {
  margin: 0 0 8px;
  font-size: 18px;
  color: #e6f1ff;
}

.publication-authors {
  color: #a0aec0;
  font-size: 14px;
  margin-bottom: 4px;
}

.publication-venue {
  color: #718096;
  font-size: 13px;
  margin-bottom: 16px;
}

.publication-links {
  display: flex;
  gap: 16px;
}

.publication-links .el-button {
  color: #4299e1;
}

/* Languages Card */
.languages-card,
.interests-card {
  background: rgba(17, 34, 64, 0.8) !important;
  border: 1px solid rgba(100, 255, 218, 0.1) !important;
}

.card-header {
  display: flex;
  align-items: center;
  gap: 12px;
}

.card-header .el-icon {
  font-size: 20px;
  color: #64ffda;
}

.card-header h3 {
  margin: 0;
  font-size: 16px;
  color: #e6f1ff;
}

.language-list {
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.language-item {
  display: flex;
  align-items: center;
  gap: 12px;
}

.language-name {
  width: 70px;
  color: #e6f1ff;
  font-size: 14px;
}

.language-level {
  flex: 1;
  height: 6px;
  background: rgba(255, 255, 255, 0.1);
  border-radius: 3px;
  overflow: hidden;
}

.level-bar {
  height: 100%;
  background: linear-gradient(90deg, #4299e1, #64ffda);
  border-radius: 3px;
}

.language-percentage {
  width: 40px;
  color: #64ffda;
  font-size: 14px;
  font-weight: 600;
}

/* Interests Grid */
.interests-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 16px;
}

.interest-item {
  display: flex;
  align-items: center;
  gap: 12px;
  padding: 12px;
  background: rgba(100, 255, 218, 0.05);
  border-radius: 8px;
  transition: all 0.3s;
}

.interest-item:hover {
  background: rgba(100, 255, 218, 0.1);
  transform: translateY(-2px);
}

.interest-item .el-icon {
  font-size: 20px;
  color: #64ffda;
}

.interest-item span {
  color: #e6f1ff;
  font-size: 14px;
}

/* Responsive Design */
@media (max-width: 1024px) {
  .resume-grid {
    grid-template-columns: 1fr;
  }

  .resume-sidebar {
    position: sticky;
    top: 0;
    z-index: 100;
    height: auto;
  }

  .sidebar-sticky {
    height: auto;
    padding: 24px;
  }

  .hero-content {
    grid-template-columns: 1fr;
  }

  .hero-visual {
    display: none;
  }
}

@media (max-width: 768px) {
  .resume-main {
    padding: 20px;
  }

  .hero-greeting {
    font-size: 32px;
  }

  .section-header h2 {
    font-size: 24px;
  }

  .key-highlights {
    grid-template-columns: 1fr;
  }
}
</style>