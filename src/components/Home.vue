<template>
  <section class="home-section" id="home">
    <div class="overlay"></div>

    <div class="container content">
      <div class="row align-items-center min-vh-100">

        <!-- LEFT CONTENT -->
        <div class="col-lg-6 text-lg-start text-center mb-5 mb-lg-0">
          <h1 class="display-4 fw-bold text-light mb-3">
            Hi, I'm <span class="highlight">Muneeb</span>
          </h1>

          <h3 class="typing-text mb-4">{{ displayedText }}</h3>

          <p class="lead text-light mb-4">
            Front-end developer crafting fast, responsive and elegant web
            experiences using Vue.js and modern JavaScript.
          </p>

          <a href="#projects" class="btn btn-outline-light btn-lg custom-btn me-3">
            View Projects
          </a>
          <a href="#contact" class="btn btn-outline-light btn-lg custom-btn">
            Contact Me
          </a>
        </div>

        <!-- RIGHT IMAGE -->
        <div class="col-lg-6 text-center">
          <img
            src="/assets/muneeb-hero.webp"
            alt="Muneeb Tariq"
            class="hero-img"
          />
        </div>

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
  }, 100)
}

function eraseRole() {
  const erasing = setInterval(() => {
    if (displayedText.value.length > 0) {
      displayedText.value = displayedText.value.slice(0, -1)
    } else {
      clearInterval(erasing)
      current = (current + 1) % roles.length
      setTimeout(typeRole, 400)
    }
  }, 50)
}

onMounted(typeRole)
</script>

<style scoped>
.home-section {
  position: relative;
  min-height: 100vh;
  background: url('https://images.unsplash.com/photo-1527689368864-3a821dbccc34?auto=format&fit=crop&w=1600&q=80')
    no-repeat center center / cover;
}

.overlay {
  position: absolute;
  inset: 0;
  background: linear-gradient(
    to bottom,
    rgba(13, 19, 33, 0.88),
    rgba(15, 23, 42, 0.95)
  );
  z-index: 1;
}

.content {
  position: relative;
  z-index: 2;
}

.highlight {
  color: #00e5ff;
}

.typing-text {
  font-size: 1.5rem;
  font-weight: 600;
  color: #00e5ff;
  min-height: 2.5rem;
}

.custom-btn {
  border-radius: 30px;
  padding: 0.75rem 2rem;
  border-color: #00e5ff;
  color: #ffffff;
  transition: all 0.3s ease;
}

.custom-btn:hover {
  background-color: #00e5ff;
  color: #0d1321;
  box-shadow: 0 0 20px rgba(0, 229, 255, 0.6);
}

.hero-img {
  max-width: 380px;
  width: 100%;
  border-radius: 20px;
  box-shadow:
    0 0 40px rgba(0, 229, 255, 0.35),
    0 30px 60px rgba(0, 0, 0, 0.6);
  transition: transform 0.4s ease;
}

.hero-img:hover {
  transform: translateY(-8px);
}

@media (max-width: 768px) {
  .display-4 {
    font-size: 2.1rem;
  }

  .typing-text {
    font-size: 1.2rem;
  }
}
</style>
