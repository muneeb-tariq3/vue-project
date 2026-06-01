<template>
  <header :class="['navbar', { scrolled: isScrolled }]">

    <div class="nav-inner">

      <!-- LOGO -->
      <div class="logo">
        Muneeb<span>.</span>
      </div>

      <!-- DESKTOP LINKS -->
      <nav class="links desktop">

        <a @click="go('Home')">Home</a>
        <a @click="go('About')">About</a>
        <a @click="go('Skills')">Skills</a>
        <a @click="go('Projects')">Projects</a>
        <a @click="go('Services')">Services</a>
        <a @click="go('Blog')">Blog</a>
        <a @click="go('Contact')">Contact</a>

      </nav>

      <!-- MOBILE BUTTON -->
      <div class="menu-btn" @click="toggleMenu">
        ☰
      </div>

    </div>

    <!-- MOBILE SIDEBAR -->
    <div class="sidebar" :class="{ open: isMenuOpen }">

      <div class="close-btn" @click="toggleMenu">×</div>

      <a @click="mobileGo('Home')">Home</a>
      <a @click="mobileGo('About')">About</a>
      <a @click="mobileGo('Skills')">Skills</a>
      <a @click="mobileGo('Projects')">Projects</a>
      <a @click="mobileGo('Services')">Services</a>
      <a @click="mobileGo('Blog')">Blog</a>
      <a @click="mobileGo('Contact')">Contact</a>

    </div>

    <!-- BACKDROP -->
    <div class="backdrop" v-if="isMenuOpen" @click="toggleMenu"></div>

  </header>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from "vue"

const emit = defineEmits(["navigate"])

const isScrolled = ref(false)
const isMenuOpen = ref(false)

const go = (section) => {
  emit("navigate", section)
}

const mobileGo = (section) => {
  emit("navigate", section)
  isMenuOpen.value = false
}

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}

/* scroll detection */
const handleScroll = () => {
  isScrolled.value = window.scrollY > 30
}

onMounted(() => {
  window.addEventListener("scroll", handleScroll)
})

onUnmounted(() => {
  window.removeEventListener("scroll", handleScroll)
})
</script>

<style scoped>

/* =========================
   NAVBAR BASE
========================= */
.navbar {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 999;

  display: flex;
  justify-content: center;
}

/* INNER */
.nav-inner {
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;

  padding: 14px 40px;

  background: rgba(255, 255, 255, 0.06);
  backdrop-filter: blur(22px);
  -webkit-backdrop-filter: blur(22px);

  border-bottom: 1px solid rgba(255, 255, 255, 0.12);

  transition: all 0.6s ease;
}

/* SCROLLED (APPLE STYLE) */
.navbar.scrolled .nav-inner {
  width: 92%;
  margin: 0 auto;

  border-radius: 0 0 28px 28px;

  background: rgba(255, 255, 255, 0.08);

  box-shadow:
    0 10px 40px rgba(0, 0, 0, 0.35),
    inset 0 1px 1px rgba(255,255,255,0.08);
}

/* =========================
   LOGO
========================= */
.logo {
  font-size: 1.3rem;
  font-weight: 700;
  color: #fff;
}

.logo span {
  color: #748CAB;
}

/* =========================
   DESKTOP LINKS
========================= */
.links {
  display: flex;
  gap: 22px;
}

.links a {
  color: #fff;
  text-decoration: none;
  cursor: pointer;
  transition: 0.3s;
  position: relative;
}

.links a::after {
  content: "";
  position: absolute;
  left: 0;
  bottom: -5px;
  width: 0%;
  height: 2px;
  background: #cfcfcf;
  transition: width 0.3s;
}

.links a:hover {
  color: #fff;
}

.links a:hover::after {
  width: 100%;
}

/* =========================
   MOBILE MENU BUTTON
========================= */
.menu-btn {
  display: none;
  font-size: 1.8rem;
  color: #fff;
  cursor: pointer;
}

/* =========================
   SIDEBAR (GLASS STYLE)
========================= */
.sidebar {
  position: fixed;
  top: 0;
  right: -280px;

  width: 260px;
  height: 100vh;

  background: rgba(13, 19, 33, 0.85);
  backdrop-filter: blur(25px);

  border-left: 1px solid rgba(255,255,255,0.1);

  display: flex;
  flex-direction: column;
  padding: 60px 20px;

  gap: 18px;

  transition: 0.4s ease;
  z-index: 1000;
}

.sidebar.open {
  right: 0;
}

/* sidebar links */
.sidebar a {
  color: #cfcfcf;
  text-decoration: none;
  font-size: 1rem;
  cursor: pointer;
  transition: 0.3s;
}

.sidebar a:hover {
  color: #fff;
  transform: translateX(5px);
}

/* close button */
.close-btn {
  position: absolute;
  top: 15px;
  right: 15px;

  font-size: 1.8rem;
  color: #fff;

  cursor: pointer;
}

/* backdrop */
.backdrop {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100vh;

  background: rgba(0,0,0,0.4);
  z-index: 999;
}

/* =========================
   RESPONSIVE
========================= */
@media (max-width: 768px) {

  .links {
    display: none;
  }

  .menu-btn {
    display: block;
  }
}
</style>
