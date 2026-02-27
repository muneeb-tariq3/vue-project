<template>
  <section class="skills-section py-5" id="skills">
    <div class="container">
      <h2 class="section-title text-center mb-5">Skills & Expertise</h2>

      <div class="row g-4">

        <!-- Frontend -->
        <div class="col-md-6 col-lg-4">
          <div class="skill-card">
            <h5>Frontend Development</h5>
            <ul>
              <li>HTML5 & Semantic Markup</li>
              <li>CSS3 & Responsive Design</li>
              <li>JavaScript (ES6+)</li>
              <li>TypeScript (Basics)</li>
              <li>Bootstrap</li>
            </ul>
          </div>
        </div>

        <!-- Frameworks -->
        <div class="col-md-6 col-lg-4">
          <div class="skill-card">
            <h5>Frameworks & Libraries</h5>
            <ul>
              <li>Vue.js (Vue 3)</li>
              <li>React.js (Basics)</li>
              <li>Single Page Applications (SPA)</li>
              <li>Component-Based Architecture</li>
            </ul>
          </div>
        </div>

        <!-- Programming -->
        <div class="col-md-6 col-lg-4">
          <div class="skill-card">
            <h5>Programming</h5>
            <ul>
              <li>JavaScript</li>
              <li>Python</li>
              <li>PHP (Familiarity via Training)</li>
            </ul>
          </div>
        </div>

        <!-- AI & Tools -->
        <div class="col-md-6 col-lg-4">
          <div class="skill-card">
            <h5>AI-Assisted Coding</h5>
            <ul>
              <li>Using AI tools to speed up development</li>
              <li>Debugging & code optimization with AI</li>
              <li>Prompt-based UI & logic generation</li>
            </ul>
          </div>
        </div>

        <!-- DevOps -->
        <div class="col-md-6 col-lg-4">
          <div class="skill-card">
            <h5>Development & OS</h5>
            <ul>
              <li>Linux (Command Line)</li>
              <li>Git & GitHub</li>
              <li>GitHub → Netlify Deployment</li>
            </ul>
          </div>
        </div>

        <!-- Database -->
        <div class="col-md-6 col-lg-4">
          <div class="skill-card">
            <h5>Database & Backend Basics</h5>
            <ul>
              <li>Database Creation (Basic)</li>
              <li>Understanding Backend Workflows</li>
              <li>API Consumption (Frontend)</li>
            </ul>
          </div>
        </div>

      </div>
    </div>
  </section>
</template>

<script setup>
// Static skills section – no JS needed (best for Lighthouse)
</script>

<style scoped>
.skills-section {
  background: linear-gradient(135deg, #0f172a, #020617);
  color: #e5e7eb;
}

.section-title {
  font-weight: 700;
  color: #f8fafc;
}

.skill-card {
  height: 100%;
  background: rgba(255, 255, 255, 0.04);
  border: 1px solid rgba(148, 163, 184, 0.2);
  border-radius: 14px;
  padding: 1.5rem;
  transition: transform 0.3s ease, border-color 0.3s ease;
}

.skill-card:hover {
  transform: translateY(-4px);
  border-color: #38bdf8;
}

.skill-card h5 {
  margin-bottom: 1rem;
  color: #38bdf8;
  font-weight: 600;
}

.skill-card ul {
  padding-left: 1rem;
  margin: 0;
}

.skill-card li {
  margin-bottom: 0.4rem;
  font-size: 0.95rem;
}
</style>