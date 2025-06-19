<template>
  <footer class="footer py-5 text-light" id="footer">
    <div class="container">
      <div class="row">

        <!-- Company & Description -->
        <div class="col-md-4 mb-4">
          <h5 class="footer-title">Muneeb‑ur‑Rehman</h5>
          <p>
            Front‑End Developer with a flair for creating modern, responsive, and user‑friendly web applications using Vue.js, Bootstrap, and Tailwind.
          </p>
        </div>

        <!-- Quick Links -->
        <div class="col-md-2 mb-4">
          <h6 class="footer-title">Quick Links</h6>
          <ul class="list-unstyled">
            <li><a href="#home" class="footer-link">Home</a></li>
            <li><a href="#about" class="footer-link">About</a></li>
            <li><a href="#projects" class="footer-link">Projects</a></li>
            <li><a href="#contact" class="footer-link">Contact</a></li>
          </ul>
        </div>

        <!-- Resources -->
        <div class="col-md-2 mb-4">
          <h6 class="footer-title">Resources</h6>
          <ul class="list-unstyled">
            <li><a href="#blog" class="footer-link">Blog</a></li>
            <li><a href="#testimonials" class="footer-link">Testimonials</a></li>
            <li><a href="/resume.pdf" class="footer-link">Resume</a></li>
            <li><a href="#services" class="footer-link">Services</a></li>
          </ul>
        </div>

        <!-- Newsletter Signup -->
        <div class="col-md-4 mb-4">
          <h6 class="footer-title">Stay Connected</h6>
          <p>Sign up to get updates on my latest projects and blog posts.</p>
          <form @submit.prevent class="d-flex">
            <input type="email" placeholder="Your email" class="form-control me-2" />
            <button type="submit" class="btn btn-accent">Subscribe</button>
          </form>
        </div>

      </div>

      <hr class="footer-separator" />

      <div class="d-flex justify-content-between align-items-center pt-3">
        <p class="mb-0">&copy; 2025 Muneeb‑ur‑Rehman. All rights reserved.</p>
        <div class="social-icons">
          <a href="#" class="social-link"><i class="bi bi-facebook"></i></a>
          <a href="#" class="social-link"><i class="bi bi-github"></i></a>
          <a href="#" class="social-link"><i class="bi bi-linkedin"></i></a>
        </div>
      </div>
    </div>
  </footer>
</template>

<script setup>
// No scripts needed (static footer)
</script>

<style scoped>
.footer {
  background-color: #1D2D44;
}

.footer-title {
  color: #F0EBD8;
  font-weight: bold;
  margin-bottom: 0.75rem;
}

.footer-link {
  color: #748CAB;
  text-decoration: none;
}
.footer-link:hover {
  color: #F0EBD8;
}

.btn-accent {
  background-color: #3E5C76;
  color: #F0EBD8;
}
.btn-accent:hover {
  background-color: #0D1321;
  color: #F0EBD8;
}

.footer-separator {
  border-color: #3E5C76;
}

.social-link {
  color: #F0EBD8;
  font-size: 1.25rem;
  margin-left: 0.75rem;
}
.social-link:hover {
  color: #748CAB;
}
</style>
