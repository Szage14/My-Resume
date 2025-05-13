<template>
  <div class="resume-container">
    <div class="resume" ref="resume">
      <!-- Header Section with Photo and Personal Info -->
      <div class="header-section">
        <div class="photo-container">
          <div v-if="!resumeData.photoUrl" class="photo-placeholder">Your Photo Here</div>
          <img v-else :src="resumeData.photoUrl" alt="Profile Photo" class="profile-photo" />
        </div>
        
        <div class="personal-info">
          <h1 class="name">{{ resumeData.fullName }}</h1>
          <h2 class="title">{{ resumeData.title }}</h2>
          <p class="summary">{{ resumeData.summary }}</p>
          
          <div class="contact-details">
            <div class="contact-item">
              <span class="contact-icon">✉️</span>
              <span>{{ resumeData.email }}</span>
            </div>
            <div class="contact-item">
              <span class="contact-icon">📱</span>
              <span>{{ resumeData.telephone }}</span>
            </div>
            <div class="contact-item">
              <span class="contact-icon">📍</span>
              <span>{{ resumeData.address }}</span>
            </div>
            <div class="contact-item">
              <span class="contact-icon">🔗</span>
              <span>
                <a :href="resumeData.linkedin" target="_blank" rel="noopener noreferrer">
                  LinkedIn Profile
                </a>
              </span>
            </div>
          </div>
        </div>
      </div>

      <!-- Main Content -->
      <div class="main-content">
        <!-- Left Column -->
        <div class="left-column">
          <!-- Career Objective -->
          <div class="section">
            <h3 class="section-title">CAREER OBJECTIVE</h3>
            <p class="career-objective">
              Aspiring Full-Stack Developer with hands-on experience in Vue.js, React, Node.js, Strapi, and Laravel, seeking to leverage strong problem-solving skills and a growth mindset to build scalable web applications. Eager to contribute to cross-functional teams, continuously learn new technologies, and drive impactful solutions that align with business goals.
            </p>
          </div>

          <!-- Workshop and Training -->
          <div class="section">
            <h3 class="section-title">WORKSHOP AND TRAINING</h3>
            <div class="training-item">
              <h4 class="training-title">Intern – Project Monitoring System (PMS)</h4>
              <span class="institution">Caraga State University-Main Campus</span>
            </div>
            <div class="training-item">
              <h4 class="training-title">Capstone-Caraga Heritage Sites Interactive Map Portal (CTSIMP)</h4>
              <span class="institution">Caraga State University-Main Campus</span>
            </div>
            <div class="training-item">
              <h4 class="training-title">ITE Competency Appraisal-Retail Management System (RMS)</h4>
              <span class="institution">Caraga State University-Main Campus</span>
            </div>
          </div>

          <!-- Education -->
          <div class="section">
            <h3 class="section-title">EDUCATION</h3>
            <div class="education-item">
              <div class="education-header">
                <h4 class="course">Bachelor of Science in Information Systems</h4>
                <span class="institution">Caraga State University-Main Campus</span>
                <span class="year">2021-Present</span>
              </div>
              <p class="education-description">
                A blend of technical depth, business understanding, and applied practice equips students with the skills for a dynamic career at the intersection of technology and management.
              </p>
            </div>
          </div>
        </div>

        <!-- Right Column -->
        <div class="right-column">
          <!-- Skills -->
          <div class="section">
            <h3 class="section-title">SKILLS</h3>
            <ul class="skills-list">
              <li>Version Control & Collaboration: Git, GitHub</li>
              <li>Document Merging: Autocrat</li>
              <li>Data Analysis: Jupyter</li>
              <li>Microsoft Office</li>
              <li>Web Development</li>
              <li>Eagerness to Learn</li>
              <li>Communication</li>
              <li>Adaptability</li>
            </ul>
          </div>

          <!-- Languages -->
          <div class="section">
            <h3 class="section-title">LANGUAGES</h3>
            <ul class="languages-list">
              <li>Filipino</li>
              <li>English</li>
              <li>Bisaya</li>
            </ul>
          </div>

          <!-- References -->
          <div class="section">
            <h3 class="section-title">REFERENCES</h3>
            <div class="references-grid">
              <div class="reference-item">
                <h4 class="referee-name">AR. Christian Dwight C. Dolotina</h4>
                <p class="referee-details">
                  Director of General Services Office, Caraga State University-Main Campus<br>
                  Email: cdwightdol27@gmail.com
                </p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ResumeTemplate',
  data() {
    return {
      resumeData: {
        // Personal Information
        fullName: 'CRISTIAN JAY T. BUQUIS',
        title: 'Aspiring Fullstack Developer',
        summary: '4th Year BSIS Student at Caraga State University.',
        photoUrl: require('@/assets/mypic-white-bg.png'), // Updated to use the provided photo
        email: 'Cjbuquis@gmail.com',
        telephone: '09472756345 / 09084782586',
        address: 'Buenavista, Agusan del Norte',
        linkedin: 'https://bit.ly/426J2H3',
      }
    };
  }
};
</script>

<style>
/* Import Lexend font */
@import url('https://fonts.googleapis.com/css2?family=Lexend:wght@400;500;600;700&display=swap');

/* Base Styles with Creative Colors */
:root {
  --primary-color: #2a3b4c;
  --accent-color: #1abc9c;
  --accent-light: #e8f8f5;
  --accent-dark: #16a085;
  --secondary-color: #e74c3c;
  --secondary-light: #fadbd8;
  --text-color: #34495e;
  --light-bg: #f9f9f9;
  --medium-gray: #ecf0f1;
  --dark-gray: #7f8c8d;
  --white: #ffffff;
  --spacing-unit: 1rem;
}

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: 'Lexend', Arial, sans-serif; /* Updated font family */
  line-height: 1.6;
  color: var(--text-color);
  background-color: var(--light-bg);
}

/* Resume Container - Optimized for single page */
.resume-container {
  max-width: 800px;
  margin: 0 auto;
  padding: 0;
  position: relative;
}

.resume {
  background-color: var(--white);
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
  padding: 15px;
  border-radius: 8px;
  overflow: hidden;
  position: relative;
  min-height: 1056px; /* Standard US Letter height */
  max-height: 1056px;
}

.resume::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 5px;
  background: linear-gradient(90deg, var(--accent-color), var(--secondary-color));
}

/* Header Section */
.header-section {
  display: flex;
  margin-bottom: 15px;
  border-bottom: 2px solid var(--accent-light);
  padding-bottom: 15px;
}

.photo-container {
  width: 120px;
  height: 120px;
  margin-right: 20px;
  overflow: hidden;
  border-radius: 50%;
  border: 3px solid var(--accent-color);
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
  flex-shrink: 0;
}

.photo-placeholder {
  width: 100%;
  height: 100%;
  background-color: var(--accent-light);
  display: flex;
  align-items: center;
  justify-content: center;
  color: var(--accent-color);
  font-size: 0.8rem;
  text-align: center;
}

.profile-photo {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.personal-info {
  flex: 1;
}

.name {
  font-size: 1.8rem;
  font-weight: 700;
  margin-bottom: 0.2rem;
  color: var(--primary-color);
  letter-spacing: 1px;
}

.title {
  font-size: 1.1rem;
  font-weight: 500;
  margin-bottom: 0.5rem;
  color: var(--accent-color);
  letter-spacing: 0.5px;
}

.summary {
  margin-bottom: 0.8rem;
  font-size: 0.85rem;
  color: var(--text-color);
  line-height: 1.5;
}

.contact-details {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 0.5rem;
}

.contact-item {
  display: flex;
  align-items: center;
  font-size: 0.8rem;
}

.contact-icon {
  margin-right: 0.4rem;
  width: 16px;
  display: inline-block;
}

/* Main Content */
.main-content {
  display: grid;
  grid-template-columns: 2fr 1fr;
  gap: 15px;
  height: calc(100% - 160px); /* Adjust based on header height */
}

/* Section Styling */
.section {
  margin-bottom: 15px;
  position: relative;
}

.section-title {
  font-size: 0.9rem;
  font-weight: 600;
  margin-bottom: 10px;
  color: var(--white);
  letter-spacing: 1.5px;
  background-color: var(--accent-color);
  padding: 0.3rem 0.8rem;
  border-radius: 4px;
  display: inline-block;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

/* Work Experience */
.experience-item, .education-item, .training-item {
  margin-bottom: 10px;
  padding: 8px;
  background-color: var(--accent-light);
  border-radius: 6px;
  border-left: 3px solid var(--accent-color);
}

.job-header, .education-header, .training-header {
  margin-bottom: 5px;
}

.job-title, .course, .training-title {
  font-weight: 600;
  font-size: 0.9rem;
  margin-bottom: 2px;
  color: var(--primary-color);
}

.job-details, .certificate-header {
  display: flex;
  justify-content: space-between;
  font-size: 0.8rem;
  color: var(--dark-gray);
  margin-bottom: 5px;
}

.company, .institution {
  color: var(--accent-dark);
  font-weight: 500;
}

.year {
  background-color: var(--accent-dark);
  color: var(--white);
  padding: 0.1rem 0.5rem;
  border-radius: 20px;
  font-size: 0.7rem;
  display: inline-block;
  margin-left: 10px; /* Add spacing between the year and the institution */
}

.job-description, .education-description, .education-learnings {
  font-size: 0.8rem;
  margin-bottom: 5px;
  line-height: 1.5;
}

.achievements {
  list-style-type: none;
  margin-left: 5px;
  font-size: 0.8rem;
}

.achievements li {
  margin-bottom: 3px;
  position: relative;
  padding-left: 15px;
}

.achievements li::before {
  content: "•";
  position: absolute;
  left: 0;
  color: var(--accent-color);
  font-weight: bold;
}

/* Skills */
.skill-item {
  margin-bottom: 8px;
}

.skill-name {
  font-size: 0.85rem;
  font-weight: 500;
  margin-bottom: 3px;
  color: var (--primary-color);
}

.skill-bar {
  height: 8px;
  background-color: var(--medium-gray);
  border-radius: 20px;
  overflow: hidden;
  box-shadow: inset 0 1px 3px rgba(0, 0, 0, 0.1);
}

.skill-level {
  height: 100%;
  background: linear-gradient(90deg, var(--accent-color), var(--accent-dark));
  border-radius: 20px;
}

/* Certificates */
.certificates-list {
  list-style-type: none;
}

.certificate-item {
  margin-bottom: 8px;
  font-size: 0.8rem;
  padding: 8px;
  background-color: var(--secondary-light);
  border-radius: 6px;
  border-left: 3px solid var(--secondary-color);
}

.certificate-name {
  font-weight: 600;
  color: var(--primary-color);
}

/* Languages */
.language-item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 8px;
  padding: 3px 0;
}

.language-name {
  font-size: 0.85rem;
  font-weight: 500;
  color: var(--primary-color);
}

.language-level {
  display: flex;
}

.language-dot {
  width: 10px;
  height: 10px;
  border-radius: 50%;
  background-color: var(--medium-gray);
  margin-left: 4px;
}

.language-dot.filled {
  background: linear-gradient(135deg, var(--accent-color), var(--accent-dark));
  box-shadow: 0 1px 2px rgba(0, 0, 0, 0.1);
}

/* References */
.references-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 8px;
}

.reference-item {
  font-size: 0.8rem;
  padding: 8px;
  background-color: var(--accent-light);
  border-radius: 6px;
  border-left: 3px solid var(--accent-color);
}

.referee-name {
  font-weight: 600;
  margin-bottom: 2px;
  color: var(--primary-color);
}

.referee-details {
  color: var(--text-color);
}

/* Print Styles - Critical for single page printing */
@media print {
  @page {
    size: letter portrait;
    margin: 0.5cm;
  }
  
  html, body {
    width: 100%;
    height: 100%;
    margin: 0;
    padding: 0;
    background-color: white;
  }
  
  .resume-container {
    width: 100%;
    height: 100%;
    margin: 0;
    padding: 0;
    box-shadow: none;
  }
  
  .resume {
    width: 100%;
    height: 100%;
    padding: 10px;
    margin: 0;
    box-shadow: none;
    border-radius: 0;
    overflow: hidden;
    page-break-inside: avoid;
  }
  
  .resume::before {
    display: block;
  }
  
  /* Ensure no page breaks within sections */
  .section, .experience-item, .education-item, 
  .training-item, .certificate-item, .reference-item {
    page-break-inside: avoid;
  }
  
  /* Reduce font sizes slightly for print */
  .name {
    font-size: 1.7rem;
  }
  
  .title {
    font-size: 1rem;
  }
  
  .section-title {
    font-size: 0.85rem;
  }
  
  .job-title, .course, .training-title {
    font-size: 0.85rem;
  }
  
  .job-description, .education-description, 
  .education-learnings, .achievements li {
    font-size: 0.75rem;
  }
  
  /* Reduce spacing */
  .section {
    margin-bottom: 12px;
  }
  
  .experience-item, .education-item, 
  .training-item, .certificate-item {
    padding: 6px;
    margin-bottom: 8px;
  }
}

/* Responsive Design */
@media (max-width: 768px) {
  .header-section {
    flex-direction: column;
    align-items: center;
    text-align: center;
  }
  
  .photo-container {
    margin-right: 0;
    margin-bottom: 15px;
  }
  
  .contact-details {
    grid-template-columns: 1fr;
    justify-items: center;
  }
  
  .main-content {
    grid-template-columns: 1fr;
  }
  
  .job-details, .certificate-header {
    flex-direction: column;
    align-items: flex-start;
  }
  
  .year {
    margin-top: 3px;
  }
}

/* Add spacing below the Career Objective section */
.career-objective {
  margin-bottom: 20px; /* Adjust this value as needed */
  padding-left: 10px; /* Add space to the left */
  padding-right: 10px; /* Add space to the right */
}
</style>