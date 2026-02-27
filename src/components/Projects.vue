<template>
  <section class="projects-section py-5" id="projects">
    <div class="container">
      <h2 class="section-title text-center mb-5">Projects</h2>

      <div class="row g-4">

        <!-- Project 1 -->
        <div class="col-md-6 col-lg-4">
          <div class="project-card">
            <h5>School Portfolio Website</h5>
            <p>
              Built a responsive portfolio website for a local school to showcase classes,
              teachers, facilities, and success stories. Integrated smooth navigation,
              interactive sections, and dynamic content cards. Added pricing cards for
              each class from Play/Nursery up to grade 10. Focused on mobile-friendly
              design, user-friendly layout, and fast loading. Created a feedback page
              to collect student and parent comments with basic security measures.
            </p>
            <p class="tech">Tech Stack: PHP, HTML5, CSS3, JS, Tailwind | Deployment: Web hosting</p>
          </div>
        </div>

        <!-- Project 2 -->
        <div class="col-md-6 col-lg-4">
          <div class="project-card">
            <h5>IMS – Institute Management System</h5>
            <p>
              Developed a complete Institute Management System as part of a small team.
              The system manages student registration, teacher profiles, course schedules,
              and exam records. Implemented responsive dashboards for both students and staff.
              Added attendance tracking, performance analysis, and secure login features.
              Backend was created using Python, frontend with Vue 3 and Bootstrap 5, and
              interactive features powered by JavaScript. Both backend and frontend were
              deployed online with proper routing and security best practices. Collaborative
              workflow ensured smooth integration and version control with GitHub.
            </p>
            <p class="tech">Tech Stack: Python, Vue 3, Bootstrap 5, JS | Deployment: Backend + Frontend Online</p>
          </div>
        </div>

        <!-- Project 3 -->
        <div class="col-md-6 col-lg-4">
          <div class="project-card">
            <h5>College Management & Landing Page</h5>
            <p>
              Designed and implemented a comprehensive college landing page with
              integrated management system to handle student, teacher, and office operations.
              Created secure login systems for students, teachers, and administration
              (MD) to monitor performance, manage salaries, and track academic progress.
              The platform ensures role-based access control, data validation, and
              protection against common security threats. The UI was designed to be
              clear, intuitive, and responsive for all devices. Focused on streamlining
              office and academic tasks while keeping data secure and easily accessible.
            </p>
            <p class="tech">Tech Stack: PHP, HTML5, CSS3, JS, Tailwind | Deployment: Online Hosting</p>
          </div>
        </div>

      </div>
    </div>
  </section>
</template>

<script setup>
// Static projects section, no JS needed
</script>

<style scoped>
.projects-section {
  background: linear-gradient(135deg, #0f172a, #020617);
  color: #e5e7eb;
  padding: 5rem 1rem;
}

.section-title {
  font-weight: 700;
  color: #22d3ee;
}

.project-card {
  background: rgba(255, 255, 255, 0.04);
  border: 1px solid rgba(34, 211, 238, 0.2);
  border-radius: 16px;
  padding: 1.5rem;
  height: 100%;
  transition: transform 0.3s ease, border-color 0.3s ease;
}

.project-card:hover {
  transform: translateY(-4px);
  border-color: #38bdf8;
}

.project-card h5 {
  color: #38bdf8;
  font-weight: 600;
  margin-bottom: 1rem;
}

.project-card p {
  color: #cbd5f5;
  font-size: 0.95rem;
}

.project-card .tech {
  margin-top: 0.75rem;
  font-weight: 500;
  color: #22d3ee;
  font-size: 0.9rem;
}
</style>