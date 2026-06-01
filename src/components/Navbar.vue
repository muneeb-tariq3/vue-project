<template>
  <header :class="['navbar', { scrolled: isScrolled }]">

    <div class="nav-inner">

      <!-- LOGO -->
      <div class="logo">Muneeb<span>.</span></div>

      <!-- LINKS -->
      <nav class="links">
        <a @click="go('Home')">Home</a>
        <a @click="go('About')">About</a>
        <a @click="go('Skills')">Skills</a>
        <a @click="go('Projects')">Projects</a>
        <a @click="go('Services')">Services</a>
        <a @click="go('Blog')">Blog</a>
        <a @click="go('Contact')">Contact</a>
      </nav>

    </div>

  </header>
</template>

<script setup>
import { ref, onMounted } from "vue"

const emit = defineEmits(["navigate"])
const isScrolled = ref(false)

const go = (section) => {
  emit("navigate", section)
}

onMounted(() => {
  window.addEventListener("scroll", () => {
    isScrolled.value = window.scrollY > 30
  })
})
</script>

<style scoped>
/* =========================
   BASE NAVBAR (FULL WIDTH MODE)
========================= */
.navbar {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;

  z-index: 999;

  display: flex;
  justify-content: center;

  padding: 12px 0;

  transition: all 0.6s cubic-bezier(0.22, 1, 0.36, 1);
}

/* INNER BAR (FULL WIDTH FEEL) */
.nav-inner {
  width: 100%;
  height: 60px;

  display: flex;
  justify-content: space-between;
  align-items: center;

  padding: 0 30px;

  background: rgba(255, 255, 255, 0.06);
  backdrop-filter: blur(22px);
  -webkit-backdrop-filter: blur(22px);

  border: 1px solid rgba(255, 255, 255, 0.12);

  box-shadow:
    0 10px 30px rgba(0, 0, 0, 0.25),
    inset 0 1px 1px rgba(255,255,255,0.08);

  transition: all 0.6s cubic-bezier(0.22, 1, 0.36, 1);
}

/* =========================
   SCROLLED STATE (APPLE FLOAT GLASS)
========================= */
.navbar.scrolled .nav-inner {
  width: 92%;
  max-width: 1100px;

  margin: 0 auto;

  border-radius: 999px;

  background: rgba(255, 255, 255, 0.08);
  backdrop-filter: blur(28px);
  -webkit-backdrop-filter: blur(28px);

  box-shadow:
    0 15px 40px rgba(0, 0, 0, 0.35),
    inset 0 1px 1px rgba(255,255,255,0.1);

  transform: translateY(6px);
}

/* =========================
   LOGO
========================= */
.logo {
  font-size: 1.2rem;
  font-weight: 700;
  color: #F0EBD8;
}

.logo span {
  color: #748CAB;
}

/* =========================
   LINKS
========================= */
.links {
  display: flex;
  gap: 22px;
}

.links a {
  cursor: pointer;
  color: #F0EBD8;
  text-decoration: none;

  font-size: 0.95rem;
  opacity: 0.8;

  transition: 0.3s ease;
  position: relative;
}

.links a:hover {
  opacity: 1;
  transform: translateY(-1px);
}

/* underline effect */
.links a::after {
  content: "";
  position: absolute;
  left: 0;
  bottom: -6px;

  width: 0%;
  height: 2px;

  background: linear-gradient(90deg, #748CAB, #F0EBD8);

  transition: width 0.3s ease;
}

.links a:hover::after {
  width: 100%;
}

/* =========================
   MOBILE
========================= */
@media (max-width: 768px) {
  .links {
    display: none;
  }

  .nav-inner {
    justify-content: center;
  }
}
</style>
