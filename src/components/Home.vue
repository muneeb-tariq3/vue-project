<template>
  <section class="home-section">

    <!-- BACKGROUND IMAGE -->
    <div class="bg"></div>

    <!-- OVERLAY -->
    <div class="overlay"></div>

    <!-- CONTENT -->
    <div class="content">

      <div class="glass-card">

        <h1 class="title">
          Hi, I'm <span class="highlight">Muneeb</span>
        </h1>

        <h3 class="typing-text">{{ displayedText }}</h3>

        <p class="text">
          I'm a <strong>15-year-old front-end developer</strong> from Pakistan who turns bold ideas into functional, elegant websites. I specialize in Vue.js, TailwindCSS, JavaScript, and responsive UI development.
        </p>

        <p class="text">
          I started coding with curiosity and a passion for design. Today, I build polished, high-performing user interfaces that are mobile-friendly, fast, and visually appealing.
        </p>

        <p class="text">
          I'm constantly learning, improving, and creating. My mission is to grow as a full-stack developer and contribute to meaningful digital products.
        </p>

        <a href="#projects" class="btn">View My Work</a>

      </div>

    </div>

  </section>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const roles = ['Web Developer', 'UI Designer', 'Freelancer']
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
      setTimeout(eraseRole, 1800)
    }
  }, 90)
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
  }, 40)
}

onMounted(typeRole)
</script>

<style scoped>

/* =========================
   SECTION
========================= */
.home-section {
  position: relative;
  min-height: 100vh;
  overflow: hidden;
  display: flex;
  align-items: center;
  justify-content: center;
}

/* =========================
   BACKGROUND IMAGE
========================= */
.bg {
  position: absolute;
  inset: 0;

  background-image: url("https://images.unsplash.com/photo-1521737604893-d14cc237f11d");
  background-size: cover;
  background-position: center;
  transform: scale(1.1);
}

/* DARK OVERLAY */
.overlay {
  position: absolute;
  inset: 0;
  background: rgba(13, 19, 33, 0.75);
}

/* =========================
   CONTENT WRAP
========================= */
.content {
  position: relative;
  z-index: 2;
  padding: 20px;
  display: flex;
  justify-content: center;
}

/* =========================
   GLASS CARD (APPLE STYLE)
========================= */
.glass-card {
  max-width: 750px;
  padding: 45px;

  background: rgba(255, 255, 255, 0.06);
  backdrop-filter: blur(25px);
  -webkit-backdrop-filter: blur(25px);

  border: 1px solid rgba(255, 255, 255, 0.12);
  border-radius: 28px;

  box-shadow:
    0 25px 70px rgba(0,0,0,0.45),
    inset 0 1px 1px rgba(255,255,255,0.08);

  text-align: center;
}

/* =========================
   TEXT STYLES
========================= */
.title {
  font-size: 2.8rem;
  color: #fff;
  margin-bottom: 10px;
}

.highlight {
  color: #748cab;
}

.typing-text {
  font-size: 1.4rem;
  color: #cfcfcf;
  margin-bottom: 20px;
  min-height: 30px;
  font-weight: 600;
}

.text {
  color: rgba(255,255,255,0.8);
  line-height: 1.6;
  margin-bottom: 15px;
}

/* =========================
   BUTTON
========================= */
.btn {
  display: inline-block;
  margin-top: 15px;

  padding: 12px 26px;
  border-radius: 14px;

  text-decoration: none;

  background: rgba(255,255,255,0.08);
  color: #fff;

  border: 1px solid rgba(255,255,255,0.15);

  transition: 0.3s ease;
}

.btn:hover {
  transform: translateY(-3px);
  background: rgba(255,255,255,0.15);
}

/* =========================
   RESPONSIVE
========================= */
@media (max-width: 768px) {

  .glass-card {
    padding: 25px;
  }

  .title {
    font-size: 2rem;
  }

  .typing-text {
    font-size: 1.1rem;
  }
}
</style>
