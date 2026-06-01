<template>
  <header :class="['navbar', { scrolled: isScrolled }]">

    <div class="nav-inner">

      <!-- LOGO -->
      <div class="logo">
        Muneeb<span>.</span>
      </div>

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
import { ref, onMounted, onUnmounted } from "vue"

const emit = defineEmits(["navigate"])
const isScrolled = ref(false)

const go = (section) => {
  emit("navigate", section)
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

/* =========================
   NAVBAR BASE (TOUCHING TOP)
========================= */
.navbar {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;

  z-index: 999;

  display: flex;
  justify-content: center;

  transition: all 0.6s cubic-bezier(0.22, 1, 0.36, 1);
}

/* INNER BAR */
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

  transition: all 0.6s cubic-bezier(0.22, 1, 0.36, 1);
}

/* =========================
   SCROLLED STATE (APPLE MORPH)
========================= */
.navbar.scrolled .nav-inner {
  width: 92%;
  margin: 0 auto;

  border-radius: 0 0 28px 28px;

  background: rgba(255, 255, 255, 0.08);
  backdrop-filter: blur(28px);

  border: 1px solid rgba(255, 255, 255, 0.12);

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
  color: #ffffff;
}

.logo span {
  color: #748CAB;
}

/* =========================
   LINKS
========================= */
.links {
  display: flex;
  gap: 24px;
}

.links a {
  color: #ffffff;
  text-decoration: none;

  font-size: 0.95rem;
  font-weight: 500;

  opacity: 0.9;

  position: relative;
  cursor: pointer;

  transition: all 0.3s ease;
}

/* hover underline */
.links a::after {
  content: "";
  position: absolute;
  left: 0;
  bottom: -6px;

  width: 0%;
  height: 2px;

  background: #ffffff;

  transition: width 0.3s ease;
}

.links a:hover {
  opacity: 1;
  transform: translateY(-1px);
}

.links a:hover::after {
  width: 100%;
}

/* =========================
   RESPONSIVE
========================= */
@media (max-width: 768px) {
  .nav-inner {
    padding: 12px 18px;
  }

  .links {
    gap: 12px;
    font-size: 0.85rem;
  }
}
</style>
