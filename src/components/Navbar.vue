<template>
  <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
    <div class="container-fluid">
      <a class="navbar-brand" href="#">Stella Vogue</a>
      <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#navbarNav"
      >
        <span class="navbar-toggler-icon"></span>
      </button>

      <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav ms-auto">
          <li class="nav-item" v-for="section in sections" :key="section">
            <a
              href="#"
              class="nav-link"
              @click.prevent="$emit('navigate', section)"
            >
              {{ section }}
            </a>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script setup>
const sections = [
  'Home',
  'About',
  'Skills',
  'Services',
  'Projects',
  'Testimonials',
  'Blog',
  'Contact'
]
</script>
