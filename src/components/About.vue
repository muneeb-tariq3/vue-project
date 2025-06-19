<template>
  <section class="about-me py-5" id="about">
    <div class="container text-light">
      <h2 class="section-title text-center mb-5">About Me</h2>
      <div class="row justify-content-center">
        <div class="col-md-8">
          <div class="about-box p-4 rounded">
            <p class="intro">
              Hello! I'm <strong class="highlight">Muneeb-ur-Rehman</strong>, a 15-year-old front-end web developer from <strong>Pakistan</strong>. I'm passionate about building modern, responsive websites using technologies like Vue.js, Tailwind CSS, and Bootstrap.
            </p>
            <ul class="info-list mt-4">
              <li><strong>Age:</strong> 15</li>
              <li><strong>Location:</strong> Pakistan</li>
              <li><strong>Phone:</strong> +92 300 6657269</li>
              <li><strong>Email:</strong> <a href="mailto:your@email.com" class="text-light">your@email.com</a></li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
// No logic required for static About section
</script>

<style scoped>
.about-me {
  background-color: #1D2D44;
}

.about-box {
  background-color: #0D1321;
  color: #F0EBD8;
  border: 1px solid #3E5C76;
}

.intro {
  font-size: 1.1rem;
  line-height: 1.7;
}

.highlight {
  color: #748CAB;
}

.info-list {
  list-style: none;
  padding: 0;
  font-size: 1rem;
}

.info-list li {
  margin-bottom: 0.5rem;
}
</style>
