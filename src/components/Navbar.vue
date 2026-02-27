<template>
  <nav class="navbar fixed-top">
    <div class="container">
      <a class="brand" href="#home">Muneeb</a>

      <ul class="nav-links">
        <li><a href="#home">Home</a></li>
        <li><a href="#about">About</a></li>
        <li><a href="#skills">Skills</a></li>
        <li><a href="#projects">Projects</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
    </div>
  </nav>
</template>

<style scoped>
.navbar {
  background: rgba(2,6,23,.85);
  backdrop-filter: blur(10px);
  padding: 1rem 0;
}
.brand {
  color: #22d3ee;
  font-weight: 700;
  text-decoration: none;
}
.nav-links {
  display: flex;
  gap: 1.5rem;
  list-style: none;
}
.nav-links a {
  color: #e5e7eb;
  text-decoration: none;
}
.nav-links a:hover {
  color: #22d3ee;
}
</style>
