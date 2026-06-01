<template>
  <header :class="['navbar', { scrolled: isScrolled }]">

    <div class="nav-inner">

      <!-- BRAND -->
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
import { ref, onMounted } from "vue"

const emit = defineEmits(["navigate"])

const isScrolled = ref(false)

const go = (section) => {
  emit("navigate", section)
}

/* scroll detection */
onMounted(() => {
  window.addEventListener("scroll", () => {
    isScrolled.value = window.scrollY > 20
  })
})
</script>

<style scoped>
/* =========================
   BASE NAVBAR (TOP STATE)
========================= */
.navbar {
  position: fixed;
  top: 12px;
  left: 0;
  right: 0;
  z-index: 999;

  display: flex;
  justify-content: center;

  transition: all 0.5s cubic-bezier(0.22, 1, 0.36, 1);
}

/* INNER GLASS BAR */
.nav-inner {
  width: 100%;
  height: 58px;

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

  border-radius: 0px;

  transition: all 0.5s cubic-bezier(0.22, 1, 0.36, 1);
}

/* =========================
   SCROLLED STATE (APPLE FLOAT BAR)
========================= */
.navbar.scrolled .nav-inner {
  width: 92%;
  margin: 0 auto;

  border-radius: 40px;

  background: rgba(255, 255, 255, 0.08);
  backdrop-filter: blur(28px);

  transform: translateY(2px);

  box-shadow:
    0 15px 45px rgba(0, 0, 0, 0.35),
    inset 0 1px 1px rgba(255,255,255,0.12);
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
  color: #F0EBD8;
  text-decoration: none;

  font-size: 0.95rem;
  opacity: 0.85;

  cursor: pointer;

  position: relative;

  transition: 0.3s ease;
}

/* hover underline */
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
  .links {
    display: none;
  }

  .nav-inner {
    justify-content: center;
  }
}
</style>
