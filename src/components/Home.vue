<template>
  <section class="hero-section" id="home">
    <div class="container text-center hero-content">
      
      <!-- Intro Text -->
      <h1 class="hero-title">Hi, I'm <span class="highlight">Muneeb</span></h1>
      <h2 class="hero-subtitle">{{ displayedText }}</h2>
      <p class="hero-desc">
        I create clean, responsive, and modern web interfaces
        using Vue.js, TailwindCSS, Bootstrap, and JavaScript.
        I focus on smooth user experiences and interactive UI.
      </p>

      <!-- Buttons -->
      <div class="hero-buttons">
        <a href="#projects" class="btn-main">View Projects</a>
        <a href="#contact" class="btn-outline">Contact Me</a>
      </div>

      <!-- Scroll Down -->
      <div class="scroll-down">
        <span></span>
        <span></span>
        <span></span>
      </div>

    </div>
  </section>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const roles = ['Frontend Developer', 'UI Designer', 'Freelancer', 'AI-Assisted Coder']
const displayedText = ref('')
let current = 0

function typeRole() {
  let text = roles[current]
  let i = 0
  displayedText.value = ''
  const typing = setInterval(() => {
    if (i < text.length) {
      displayedText.value += text[i]
      i++
    } else {
      clearInterval(typing)
      setTimeout(eraseRole, 2000)
    }
  }, 100)
}

function eraseRole() {
  const erasing = setInterval(() => {
    if (displayedText.value.length > 0) {
      displayedText.value = displayedText.value.slice(0, -1)
    } else {
      clearInterval(erasing)
      current = (current + 1) % roles.length
      setTimeout(typeRole, 300)
    }
  }, 50)
}

onMounted(typeRole)
</script>

<style scoped>
/* Background gradient with soft animated particles */
.hero-section {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  background: linear-gradient(135deg, #0f172a, #020617);
  overflow: hidden;
}

/* Particle animation using pseudo-elements */
.hero-section::before {
  content: '';
  position: absolute;
  width: 200%;
  height: 200%;
  top: -50%;
  left: -50%;
  background: radial-gradient(#38bdf8 1px, transparent 1px);
  background-size: 50px 50px;
  animation: moveParticles 30s linear infinite;
  opacity: 0.1;
  z-index: 0;
}

@keyframes moveParticles {
  0% { transform: translate(0, 0) rotate(0deg); }
  100% { transform: translate(50px, 50px) rotate(360deg); }
}

/* Content */
.hero-content {
  position: relative;
  z-index: 1;
  color: #e5e7eb;
  max-width: 700px;
  animation: fadeInUp 1.5s ease forwards;
}

@keyframes fadeInUp {
  0% { opacity: 0; transform: translateY(40px); }
  100% { opacity: 1; transform: translateY(0); }
}

/* Titles */
.hero-title {
  font-size: 3rem;
  font-weight: 700;
  color: #22d3ee;
  margin-bottom: 0.5rem;
  animation: fadeInDown 1.5s ease forwards;
}
.hero-subtitle {
  font-size: 1.8rem;
  color: #cbd5f5;
  font-weight: 500;
  min-height: 2rem;
  margin-bottom: 1rem;
}
.hero-desc {
  color: #94a3b8;
  margin-bottom: 2rem;
}

/* Buttons */
.hero-buttons a {
  display: inline-block;
  margin: 0.5rem 0.5rem;
  padding: 0.8rem 2rem;
  border-radius: 30px;
  font-weight: 600;
  transition: all 0.3s ease;
  text-decoration: none;
}
.btn-main {
  background-color: #22d3ee;
  color: #020617;
}
.btn-main:hover {
  background-color: #38bdf8;
  transform: scale(1.05);
}
.btn-outline {
  border: 2px solid #22d3ee;
  color: #22d3ee;
}
.btn-outline:hover {
  background-color: #22d3ee;
  color: #020617;
  transform: scale(1.05);
}

/* Scroll down animation */
.scroll-down {
  position: absolute;
  bottom: 20px;
  left: 50%;
  transform: translateX(-50%);
  display: flex;
  flex-direction: column;
  gap: 5px;
}
.scroll-down span {
  width: 6px;
  height: 6px;
  background: #22d3ee;
  border-radius: 50%;
  animation: scrollBounce 1.5s infinite;
}
.scroll-down span:nth-child(2) {
  animation-delay: 0.3s;
}
.scroll-down span:nth-child(3) {
  animation-delay: 0.6s;
}
@keyframes scrollBounce {
  0%, 80%, 100% { transform: translateY(0); opacity: 0.4; }
  40% { transform: translateY(12px); opacity: 1; }
}

/* Fade in down animation for title */
@keyframes fadeInDown {
  0% { opacity: 0; transform: translateY(-30px); }
  100% { opacity: 1; transform: translateY(0); }
}

/* Responsive */
@media (max-width: 768px) {
  .hero-title { font-size: 2rem; }
  .hero-subtitle { font-size: 1.2rem; }
  .hero-desc { font-size: 0.9rem; }
}
</style>