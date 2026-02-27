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

.footer {
  background: linear-gradient(180deg, #020617, #0b1120);
  border-top: 1px solid rgba(34, 211, 238, 0.15);
}

.footer-title {
  color: #e5e7eb;
  font-weight: 600;
  margin-bottom: 0.75rem;
}

.footer p {
  color: #94a3b8;
  font-size: 0.95rem;
}

.footer-link {
  color: #cbd5f5;
  text-decoration: none;
  position: relative;
  transition: color 0.3s ease;
}

.footer-link::after {
  content: '';
  position: absolute;
  left: 0;
  bottom: -3px;
  width: 0%;
  height: 2px;
  background: #22d3ee;
  transition: width 0.3s ease;
}

.footer-link:hover {
  color: #22d3ee;
}

.footer-link:hover::after {
  width: 100%;
}

.btn-accent {
  background-color: #22d3ee;
  color: #020617;
  border-radius: 20px;
  font-weight: 600;
  transition: all 0.3s ease;
}

.btn-accent:hover {
  background-color: #38e8ff;
  box-shadow: 0 0 18px rgba(34, 211, 238, 0.6);
}

.footer-separator {
  border-color: rgba(34, 211, 238, 0.15);
}

.social-icons {
  display: flex;
  gap: 1rem;
}

.social-link {
  color: #cbd5f5;
  font-size: 1.3rem;
  transition: transform 0.3s ease, color 0.3s ease;
}

.social-link:hover {
  color: #22d3ee;
  transform: translateY(-4px);
}