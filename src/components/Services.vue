<template>
  <section class="services-section" id="services">

    <div class="container">

      <!-- TITLE -->
      <h2 class="title">Services</h2>

      <!-- MAIN MESSAGE -->
      <p class="subtitle">
        I am currently seeking an internship to gain hands-on practical experience in tools, systems, teams, and real-world development challenges.
      </p>

      <!-- GLASS GRID -->
      <div class="services-grid">

        <div class="glass-card service-card">

          <h3>Frontend Development</h3>
          <p>
            Building responsive, fast, and interactive user interfaces using modern frameworks and clean UI architecture.
          </p>

        </div>

        <div class="glass-card service-card">

          <h3>UI Engineering</h3>
          <p>
            Translating designs into pixel-perfect, responsive interfaces with strong focus on usability and performance.
          </p>

        </div>

        <div class="glass-card service-card">

          <h3>Web Application Development</h3>
          <p>
            Developing modern web applications with scalable structure, reusable components, and API integration.
          </p>

        </div>

      </div>

    </div>

  </section>
</template>

<script setup>
import { onMounted } from "vue"

/* 3D hover effect */
onMounted(() => {
  const cards = document.querySelectorAll(".service-card")

  cards.forEach((card) => {
    card.addEventListener("mousemove", (e) => {
      const rect = card.getBoundingClientRect()

      const x = e.clientX - rect.left
      const y = e.clientY - rect.top

      const rotateX = -(y / rect.height - 0.5) * 8
      const rotateY = (x / rect.width - 0.5) * 8

      card.style.transform = `
        perspective(1000px)
        rotateX(${rotateX}deg)
        rotateY(${rotateY}deg)
        translateY(-6px)
      `

      card.style.setProperty("--x", `${x}px`)
      card.style.setProperty("--y", `${y}px`)
    })

    card.addEventListener("mouseleave", () => {
      card.style.transform =
        "perspective(1000px) rotateX(0deg) rotateY(0deg)"
    })
  })
})
</script>

<style scoped>
.services-section {
  background: #0D1321;
  padding: 80px 20px;
  color: #F0EBD8;
  position: relative;
  overflow: hidden;
}

/* background glow (Apple style depth) */
.services-section::before,
.services-section::after {
  content: "";
  position: absolute;
  width: 300px;
  height: 300px;
  filter: blur(120px);
  z-index: 0;
}

.services-section::before {
  background: #3E5C76;
  top: -100px;
  left: -100px;
  opacity: 0.4;
}

.services-section::after {
  background: #748CAB;
  bottom: -100px;
  right: -100px;
  opacity: 0.3;
}

/* TITLE */
.title {
  text-align: center;
  font-size: 2.8rem;
  font-weight: 800;

  background: linear-gradient(90deg, #F0EBD8, #748CAB);
  -webkit-background-clip: text;
  color: transparent;

  position: relative;
  z-index: 2;
}

/* SUBTITLE */
.subtitle {
  text-align: center;
  max-width: 700px;
  margin: 20px auto 50px auto;

  opacity: 0.85;
  line-height: 1.6;

  position: relative;
  z-index: 2;
}

/* GRID */
.services-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
  gap: 25px;

  position: relative;
  z-index: 2;
}

/* GLASS CARD */
.glass-card {
  padding: 25px;
  border-radius: 22px;

  background: rgba(255, 255, 255, 0.06);
  backdrop-filter: blur(25px);
  -webkit-backdrop-filter: blur(25px);

  border: 1px solid rgba(255, 255, 255, 0.12);

  box-shadow:
    0 15px 40px rgba(0, 0, 0, 0.35),
    inset 0 1px 1px rgba(255,255,255,0.08);

  transition: transform 0.3s ease;
  overflow: hidden;
}

/* hover glow */
.glass-card::after {
  content: "";
  position: absolute;
  width: 250px;
  height: 250px;

  background: radial-gradient(circle, rgba(116,140,171,0.3), transparent 70%);

  left: var(--x, 50%);
  top: var(--y, 50%);
  transform: translate(-50%, -50%);

  opacity: 0;
  transition: opacity 0.3s ease;
  pointer-events: none;
}

.glass-card:hover::after {
  opacity: 1;
}

/* TEXT */
.service-card h3 {
  color: #748CAB;
  font-size: 1.3rem;
  margin-bottom: 10px;
}

.service-card p {
  font-size: 0.95rem;
  line-height: 1.6;
  opacity: 0.9;
}

/* RESPONSIVE */
@media (max-width: 768px) {
  .title {
    font-size: 2.2rem;
  }
}
</style>
