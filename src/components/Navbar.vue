<template>
  <header :class="['navbar', { scrolled: isScrolled }]">

    <div class="nav-inner">

      <!-- LOGO -->
      <div class="logo">
        Muneeb<span>.</span>
      </div>

      <!-- LINKS -->
      <nav class="nav-links">
        <a href="#About">About</a>
        <a href="#Skills">Skills</a>
        <a href="#Projects">Projects</a>
        <a href="#Contact">Contact</a>
      </nav>

    </div>

  </header>
</template>

<script setup>
import { ref, onMounted } from "vue"

const isScrolled = ref(false)

onMounted(() => {
  window.addEventListener("scroll", () => {
    isScrolled.value = window.scrollY > 40
  })
})
</script>

<style scoped>
/* =========================
   BASE NAVBAR (GLASS MODE)
========================= */
.navbar {
  position: fixed;
  top: 15px;
  left: 0;
  right: 0;
  z-index: 999;

  display: flex;
  justify-content: center;

  transition: all 0.4s ease;
}

/* INNER GLASS CONTAINER */
.nav-inner {
  width: 92%;
  max-width: 1100px;

  display: flex;
  justify-content: space-between;
  align-items: center;

  padding: 14px 25px;

  background: rgba(255, 255, 255, 0.06);
  backdrop-filter: blur(22px);
  -webkit-backdrop-filter: blur(22px);

  border: 1px solid rgba(255, 255, 255, 0.12);

  box-shadow:
    0 10px 30px rgba(0, 0, 0, 0.25),
    inset 0 1px 1px rgba(255,255,255,0.08);

  border-radius: 18px;

  transition: all 0.5s cubic-bezier(0.22, 1, 0.36, 1);
}

/* =========================
   SCROLL STATE (APPLE EFFECT)
========================= */
.navbar.scrolled .nav-inner {
  border-radius: 40px;

  background: rgba(255, 255, 255, 0.09);
  backdrop-filter: blur(28px);

  transform: scale(0.98);

  box-shadow:
    0 12px 40px rgba(0, 0, 0, 0.35),
    inset 0 1px 2px rgba(255,255,255,0.12);
}

/* =========================
   LOGO
========================= */
.logo {
  font-size: 1.3rem;
  font-weight: 700;
  color: #F0EBD8;
  letter-spacing: 1px;
}

.logo span {
  color: #748CAB;
}

/* =========================
   LINKS
========================= */
.nav-links {
  display: flex;
  gap: 22px;
}

.nav-links a {
  text-decoration: none;
  color: #F0EBD8;
  font-size: 0.95rem;

  position: relative;
  opacity: 0.85;

  transition: 0.3s ease;
}

/* hover glow underline */
.nav-links a::after {
  content: "";
  position: absolute;
  left: 0;
  bottom: -6px;

  width: 0%;
  height: 2px;

  background: linear-gradient(90deg, #748CAB, #F0EBD8);

  transition: width 0.3s ease;
}

.nav-links a:hover {
  opacity: 1;
  transform: translateY(-1px);
}

.nav-links a:hover::after {
  width: 100%;
}

/* =========================
   RESPONSIVE
========================= */
@media (max-width: 768px) {
  .nav-links {
    display: none;
  }

  .nav-inner {
    justify-content: center;
  }
}
</style>
