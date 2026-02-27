<template>
  <section class="about-section" id="about">
    <div class="container">
      <h2 class="section-title text-center">About Me</h2>

      <div class="row align-items-center mt-5">

        <!-- LEFT CONTENT -->
        <div class="col-lg-7 text-light mb-4 mb-lg-0">
          <p class="about-intro">
            I'm <span class="accent">Muneeb-ur-Rehman</span>, a passionate
            front-end developer from Pakistan who enjoys building modern,
            responsive, and user-focused web interfaces.
          </p>

          <p class="about-text">
            I specialize in creating clean UI designs and smooth user
            experiences using <strong>Vue.js</strong>, <strong>JavaScript</strong>,
            <strong>Bootstrap</strong>, and <strong>Tailwind CSS</strong>.
            I focus on performance, responsiveness, and writing readable,
            maintainable code.
          </p>

          <p class="about-text">
            I started my journey with curiosity and creativity, and I’m
            constantly learning new tools and best practices to grow as a
            full-stack developer and work on impactful digital products.
          </p>
        </div>

        <!-- RIGHT INFO CARD -->
        <div class="col-lg-5">
          <div class="info-card">
            <ul>
              <li><span>Age:</span> 15</li>
              <li><span>Location:</span> Pakistan</li>
              <li><span>Email:</span> your@email.com</li>
              <li><span>Phone:</span> +92 300 6657269</li>
              <li><span>Availability:</span> Open for projects</li>
            </ul>
          </div>
        </div>

      </div>
    </div>
  </section>
</template>

<script setup>
// Static About section
</script>

<style scoped>
.about-section {
  background: linear-gradient(180deg, #020617, #0b1120);
  padding: 5rem 1rem;
}

.section-title {
  font-size: 2.4rem;
  font-weight: 700;
  color: #ffffff;
}

.accent {
  color: #22d3ee;
  font-weight: 600;
}

.about-intro {
  font-size: 1.2rem;
  line-height: 1.8;
  margin-bottom: 1.5rem;
  color: #e5e7eb;
}

.about-text {
  font-size: 1rem;
  line-height: 1.7;
  color: #cbd5f5;
  margin-bottom: 1rem;
}

.info-card {
  background: rgba(2, 6, 23, 0.8);
  border: 1px solid rgba(34, 211, 238, 0.2);
  border-radius: 18px;
  padding: 2rem;
  box-shadow: 0 0 30px rgba(34, 211, 238, 0.15);
}

.info-card ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

.info-card li {
  display: flex;
  justify-content: space-between;
  padding: 0.6rem 0;
  color: #e5e7eb;
  border-bottom: 1px solid rgba(34, 211, 238, 0.1);
}

.info-card li:last-child {
  border-bottom: none;
}

.info-card span {
  color: #22d3ee;
  font-weight: 500;
}

@media (max-width: 768px) {
  .section-title {
    font-size: 2rem;
  }

  .about-intro {
    font-size: 1.1rem;
  }
}
</style>