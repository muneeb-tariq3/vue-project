<script setup>
import { ref } from 'vue'

import Navbar from './components/Navbar.vue'
import Home from './components/Home.vue'
import About from './components/About.vue'
import Skills from './components/Skills.vue'
import Services from './components/Services.vue'
import Projects from './components/Projects.vue'
import Testimonials from './components/Testimonials.vue'
import Blog from './components/Blog.vue'
import Contact from './components/Contact.vue'
import Footer from './components/Footer.vue'

// Track the currently active section
const activeSection = ref('Home')

// Function to switch sections
function setSection(section) {
  activeSection.value = section
}
</script>

<template>
  <!-- Pass the section switcher function to navbar -->
  <Navbar @navigate="setSection" />

  <!-- Show only the active section -->
  <Home v-if="activeSection === 'Home'" />
  <About v-if="activeSection === 'About'" />
  <Skills v-if="activeSection === 'Skills'" />
  <Services v-if="activeSection === 'Services'" />
  <Projects v-if="activeSection === 'Projects'" />
  <Testimonials v-if="activeSection === 'Testimonials'" />
  <Blog v-if="activeSection === 'Blog'" />
  <Contact v-if="activeSection === 'Contact'" />
  <Footer />
</template>
