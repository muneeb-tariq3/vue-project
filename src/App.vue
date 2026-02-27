<template>
  <Navbar />
  <slot /> <!-- Current page content -->
  <Footer />
</template>

<script setup>
import Navbar from './components/Navbar.vue'
import Footer from './components/Footer.vue'
</script>