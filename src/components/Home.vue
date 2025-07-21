<template>
  <section class="home-section d-flex align-items-center" id="home">
    <div class="overlay"></div>
    <div class="container text-center content">
      <h1 class="display-4 fw-bold text-light mb-3">
        Hi, I'm <span class="highlight">Muneeb</span>
      </h1>
      <h3 class="typing-text mb-4">{{ displayedText }}</h3>

      <p class="lead text-light">
        I'm a <strong>15-year-old front-end developer</strong> from Pakistan who turns bold ideas into functional, elegant websites. I specialize in Vue.js, TailwindCSS, JavaScript, and responsive UI development.
      </p>

      <p class="text-light mb-3">
        I started coding with curiosity and a passion for design. Today, I build polished, high-performing user interfaces that are mobile-friendly, fast, and visually appealing. Whether it's a portfolio, a business website, or an interactive web app — I aim for pixel-perfect detail and smooth user experiences.
      </p>

      <p class="text-light mb-4">
        I'm constantly learning, improving, and creating. My mission is to grow as a full-stack developer and contribute to meaningful digital products that solve real-world problems.
      </p>

      <a href="#projects" class="btn btn-outline-light btn-lg custom-btn">View My Work</a>
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
      setTimeout(() => {
        eraseRole()
      }, 2000)
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
.home-section {
  position: relative;
  min-height: 100vh;
  background: url('https://images.unsplash.com/photo-1527689368864-3a821dbccc34?auto=format&fit=crop&w=1600&q=80')
    no-repeat center center / cover;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 4rem 1rem;
  color: #f0ebd8;
}

.overlay {
  position: absolute;
  inset: 0;
  background: linear-gradient(to bottom, rgba(13, 19, 33, 0.85), rgba(29, 45, 68, 0.9));
  z-index: 1;
}

.content {
  position: relative;
  z-index: 2;
}

.highlight {
  color: #748cab;
}

.typing-text {
  font-size: 1.5rem;
  color: #3e5c76;
  font-weight: 600;
  min-height: 2.5rem;
  height: 2.5rem;
}

.custom-btn {
  border-radius: 30px;
  padding: 0.75rem 2rem;
  border-color: #748cab;
  color: #f0ebd8;
  transition: all 0.3s ease;
}

.custom-btn:hover {
  background-color: #748cab;
  color: #0d1321;
  border-color: #748cab;
}

@media (max-width: 768px) {
  .display-4 {
    font-size: 2rem;
  }
  .typing-text {
    font-size: 1.2rem;
  }
}
</style>
