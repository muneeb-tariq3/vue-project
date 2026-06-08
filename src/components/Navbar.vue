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

/* ================= NAVBAR BASE ================= */
.navbar {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 999;

  display: flex;
  justify-content: center;
}

/* INNER GLASS BAR */
.nav-inner {
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;

  padding: 14px 40px;

  background: rgba(255, 255, 255, 0.06);
  backdrop-filter: blur(25px);
  -webkit-backdrop-filter: blur(25px);

  border-bottom: 1px solid rgba(255, 255, 255, 0.12);

  transition: all 0.5s ease;
}

/* SCROLLED APPLE STYLE */
.navbar.scrolled .nav-inner {
  width: 92%;
  margin: 0 auto;

  border-radius: 0 0 28px 28px;

  background: rgba(255, 255, 255, 0.08);

  box-shadow: 0 10px 40px rgba(0, 0, 0, 0.35);
}

/* ================= LOGO ================= */
.logo {
  font-size: 1.3rem;
  font-weight: 700;
  color: #fff;
}

.logo span {
  color: #748CAB;
}

/* ================= LINKS FIX ================= */
.links {
  display: flex;
  gap: 22px;
}

.links a,
.sidebar a {
  color: #f5f7fa !important; /* FIXED VISIBILITY */
  text-decoration: none;
  cursor: pointer;
  transition: 0.3s;
  font-weight: 500;
}

.links a {
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
  color: #ffffff;
}

.links a:hover::after {
  width: 100%;
}

/* ================= MOBILE ================= */
.menu-btn {
  display: none;
  font-size: 1.8rem;
  color: #fff;
  cursor: pointer;
}

/* ================= SIDEBAR ================= */
.sidebar {
  position: fixed;
  top: 0;
  right: -280px;

  width: 260px;
  height: 100vh;

  background: rgba(13, 19, 33, 0.9);
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

.sidebar a:hover {
  transform: translateX(6px);
}

/* CLOSE BTN */
.close-btn {
  position: absolute;
  top: 15px;
  right: 15px;

  font-size: 1.8rem;
  color: #fff;
  cursor: pointer;
}

/* BACKDROP */
.backdrop {
  position: fixed;
  inset: 0;
  background: rgba(0,0,0,0.4);
  z-index: 999;
}

/* ================= RESPONSIVE ================= */
@media (max-width: 768px) {
  .links {
    display: none;
  }

  .menu-btn {
    display: block;
  }
}
</style>
