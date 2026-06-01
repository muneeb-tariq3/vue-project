<template>
  <footer class="footer" id="footer">

    <div class="footer-glass">

      <!-- TOP SECTION -->
      <div class="footer-grid">

        <!-- BRAND -->
        <div class="col">
          <h3 class="logo">Muneeb-ur-Rehman</h3>
          <p class="desc">
            Front-End Developer focused on building modern, responsive,
            and user-friendly web applications using Vue.js and modern web technologies.
          </p>
        </div>

        <!-- QUICK LINKS -->
        <div class="col">
          <h4>Quick Links</h4>
          <a href="#home">Home</a>
          <a href="#about">About</a>
          <a href="#projects">Projects</a>
          <a href="#skills">Skills</a>
          <a href="#contact">Contact</a>
        </div>

        <!-- RESOURCES (CLEANED) -->
        <div class="col">
          <h4>Resources</h4>
          <a href="#blog">Blog</a>
          <a href="#services">Services</a>
        </div>

        <!-- CONNECT -->
        <div class="col">
          <h4>Stay Connected</h4>
          <p class="small">
            Get updates about my latest projects and development work.
          </p>

          <form class="form">
            <input type="email" placeholder="Your email" />
            <button type="submit">Subscribe</button>
          </form>
        </div>

      </div>

      <div class="divider"></div>

      <!-- BOTTOM BAR -->
      <div class="bottom">

        <p>© 2025 Muneeb-ur-Rehman. All rights reserved.</p>

        <div class="socials">
          <a href="https://github.com/muneeb-tariq3" target="_blank">GitHub</a>
          <a href="mailto:muneebtariq841@gmail.com">Email</a>
          <a href="#home">Portfolio</a>
        </div>

      </div>

    </div>

  </footer>
</template>

<script setup>
// static footer
</script>

<style scoped>
/* =======================
   FOOTER BACKGROUND
======================= */
.footer {
  background: #0D1321;
  padding: 60px 20px;
  color: #F0EBD8;
}

/* =======================
   GLASS CONTAINER
======================= */
.footer-glass {
  max-width: 1100px;
  margin: auto;

  background: rgba(255, 255, 255, 0.05);
  backdrop-filter: blur(25px);
  -webkit-backdrop-filter: blur(25px);

  border: 1px solid rgba(255, 255, 255, 0.12);
  border-radius: 25px;

  padding: 40px;

  box-shadow:
    0 15px 40px rgba(0, 0, 0, 0.35),
    inset 0 1px 1px rgba(255,255,255,0.08);
}

/* =======================
   GRID LAYOUT
======================= */
.footer-grid {
  display: grid;
  grid-template-columns: 2fr 1fr 1fr 1.2fr;
  gap: 30px;
}

/* =======================
   BRAND
======================= */
.logo {
  font-size: 1.4rem;
  color: #748CAB;
  margin-bottom: 10px;
}

.desc {
  font-size: 0.9rem;
  opacity: 0.85;
  line-height: 1.6;
}

/* =======================
   LINKS
======================= */
.col h4 {
  margin-bottom: 10px;
  color: #748CAB;
}

.col a {
  display: block;
  text-decoration: none;
  color: #F0EBD8;
  opacity: 0.75;

  margin-bottom: 8px;

  transition: 0.3s;
}

.col a:hover {
  opacity: 1;
  transform: translateX(3px);
}

/* =======================
   FORM
======================= */
.form {
  display: flex;
  margin-top: 10px;
}

.form input {
  flex: 1;
  padding: 8px 10px;

  border: none;
  outline: none;

  border-radius: 8px 0 0 8px;
}

.form button {
  padding: 8px 12px;

  border: none;
  cursor: pointer;

  background: #748CAB;
  color: #0D1321;

  border-radius: 0 8px 8px 0;

  transition: 0.3s;
}

.form button:hover {
  background: #F0EBD8;
}

/* =======================
   DIVIDER
======================= */
.divider {
  height: 1px;
  background: rgba(255,255,255,0.15);
  margin: 30px 0;
}

/* =======================
   BOTTOM BAR
======================= */
.bottom {
  display: flex;
  justify-content: space-between;
  align-items: center;

  font-size: 0.85rem;
  opacity: 0.85;
}

.socials a {
  margin-left: 15px;
  text-decoration: none;
  color: #F0EBD8;

  opacity: 0.75;
  transition: 0.3s;
}

.socials a:hover {
  opacity: 1;
  color: #748CAB;
}

/* =======================
   RESPONSIVE
======================= */
@media (max-width: 900px) {
  .footer-grid {
    grid-template-columns: 1fr;
  }

  .bottom {
    flex-direction: column;
    gap: 10px;
  }
}
</style>
