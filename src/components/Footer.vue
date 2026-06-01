<template>
  <footer class="footer">

    <div class="container">

      <!-- TOP SECTION -->
      <div class="top">

        <!-- BRAND -->
        <div class="brand">
          <h2>Muneeb<span>.</span></h2>
          <p>
            Frontend developer focused on building modern UI systems and gaining real-world development experience.
          </p>
        </div>

        <!-- NAV LINKS -->
        <div class="links">
          <h4>Navigation</h4>
          <a @click="go('Home')">Home</a>
          <a @click="go('About')">About</a>
          <a @click="go('Skills')">Skills</a>
          <a @click="go('Projects')">Projects</a>
          <a @click="go('Services')">Services</a>
          <a @click="go('Contact')">Contact</a>
        </div>

        <!-- CONTACT -->
        <div class="contact">
          <h4>Contact</h4>
          <p class="email">muneebtariq841@gmail.com</p>
          <a href="https://github.com/muneeb-tariq3" target="_blank">
            GitHub Profile
          </a>
        </div>

      </div>

      <!-- DIVIDER -->
      <div class="divider"></div>

      <!-- BOTTOM -->
      <div class="bottom">
        <p>© 2026 Muneeb. All rights reserved.</p>
        <p class="note">
          Seeking an internship to gain hands-on experience in tools, systems, teams, and real-world development challenges.
        </p>
      </div>

    </div>

  </footer>
</template>

<script setup>
const emit = defineEmits(["navigate"])

const go = (section) => {
  emit("navigate", section)
}
</script>

<style scoped>
/* =========================
   BASE FOOTER
========================= */
.footer {
  background: #0D1321;
  color: #F0EBD8;
  padding: 70px 20px;
}

/* subtle background depth */
.footer::before {
  content: "";
  position: absolute;
  inset: 0;
  background: radial-gradient(circle at top, rgba(116,140,171,0.12), transparent 60%);
  z-index: 0;
}

/* =========================
   LAYOUT
========================= */
.container {
  position: relative;
  z-index: 2;
  max-width: 1100px;
  margin: auto;
}

/* TOP GRID */
.top {
  display: grid;
  grid-template-columns: 2fr 1fr 1fr;
  gap: 40px;
}

/* BRAND */
.brand h2 {
  font-size: 1.8rem;
  margin-bottom: 10px;
}

.brand h2 span {
  color: #748CAB;
}

.brand p {
  opacity: 0.8;
  line-height: 1.6;
  font-size: 0.95rem;
}

/* HEADINGS */
h4 {
  color: #748CAB;
  margin-bottom: 12px;
  font-size: 1rem;
}

/* LINKS */
.links a,
.contact a {
  display: block;
  color: #F0EBD8;
  opacity: 0.75;
  text-decoration: none;
  margin-bottom: 8px;
  cursor: pointer;
  transition: 0.3s ease;
}

.links a:hover,
.contact a:hover {
  opacity: 1;
  transform: translateX(4px);
}

/* EMAIL */
.email {
  opacity: 0.85;
  margin-bottom: 10px;
}

/* DIVIDER */
.divider {
  height: 1px;
  background: rgba(255,255,255,0.1);
  margin: 30px 0;
}

/* BOTTOM */
.bottom {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 10px;

  font-size: 0.85rem;
  opacity: 0.7;
}

/* NOTE (internship line) */
.note {
  max-width: 500px;
}

/* =========================
   RESPONSIVE
========================= */
@media (max-width: 768px) {
  .top {
    grid-template-columns: 1fr;
    text-align: center;
  }

  .links a,
  .contact a {
    display: inline-block;
    margin: 5px 10px;
  }

  .bottom {
    justify-content: center;
    text-align: center;
  }
}
</style>
