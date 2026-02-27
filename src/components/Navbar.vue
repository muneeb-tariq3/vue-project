<template>
  <nav class="navbar navbar-expand-lg fixed-top navbar-dark glass-nav">
    <div class="container">
      <a class="navbar-brand fw-bold" href="#home">Muneeb</a>

      <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#mainNav"
      >
        <span class="navbar-toggler-icon"></span>
      </button>

      <div class="collapse navbar-collapse" id="mainNav">
        <ul class="navbar-nav ms-auto mb-2 mb-lg-0">
          <li class="nav-item">
            <a class="nav-link" href="#home">Home</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#about">About</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#projects">Projects</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#contact">Contact</a>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<style scoped>
.glass-nav {
  background: rgba(2, 6, 23, 0.75);
  backdrop-filter: blur(12px);
  border-bottom: 1px solid rgba(34, 211, 238, 0.15);
}

.navbar-brand {
  color: #22d3ee;
  letter-spacing: 0.5px;
}

.nav-link {
  color: #e5e7eb !important;
  font-weight: 500;
  margin-left: 1rem;
  transition: color 0.3s ease;
}

.nav-link:hover {
  color: #22d3ee !important;
}
</style>
