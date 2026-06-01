<template>
  <section class="blog-section" id="blog">

    <div class="container">

      <!-- TITLE -->
      <h2 class="title">Blog</h2>

      <!-- GLASS CARD -->
      <div class="glass-card">

        <h3 class="message">
          No blog by Muneeb yet!
        </h3>

        <p class="subtext">
          This space will soon contain thoughts, tutorials, and development insights from my journey as a developer.
        </p>

      </div>

    </div>

  </section>
</template>

<script setup>
// static page - no logic needed
</script>

<style scoped>
.blog-section {
  background: #0D1321;
  padding: 80px 20px;
  color: #F0EBD8;
}

/* TITLE */
.title {
  text-align: center;
  font-size: 2.6rem;
  font-weight: 800;

  background: linear-gradient(90deg, #F0EBD8, #748CAB);
  -webkit-background-clip: text;
  color: transparent;

  margin-bottom: 40px;
}

/* GLASS CARD */
.glass-card {
  max-width: 700px;
  margin: auto;

  padding: 40px;
  text-align: center;

  background: rgba(255, 255, 255, 0.06);
  backdrop-filter: blur(25px);
  -webkit-backdrop-filter: blur(25px);

  border: 1px solid rgba(255, 255, 255, 0.12);
  border-radius: 22px;

  box-shadow:
    0 20px 50px rgba(0, 0, 0, 0.35),
    inset 0 1px 1px rgba(255,255,255,0.08);
}

/* MESSAGE */
.message {
  font-size: 1.6rem;
  color: #748CAB;
  margin-bottom: 10px;
}

/* SUBTEXT */
.subtext {
  font-size: 0.95rem;
  opacity: 0.85;
  line-height: 1.6;
}

/* RESPONSIVE */
@media (max-width: 768px) {
  .title {
    font-size: 2.2rem;
  }

  .glass-card {
    padding: 25px;
  }

  .message {
    font-size: 1.3rem;
  }
}
</style>
