<template>
  <section class="projects-section" id="projects">

    <div class="container">

      <!-- TITLE -->
      <h2 class="title">Projects</h2>
      <p class="subtitle">
        A collection of real-world applications and experiments built over my development journey.
      </p>

      <!-- GRID -->
      <div class="projects-grid">

        <div
          class="glass-card project-card"
          v-for="(project, index) in projects"
          :key="index"
        >

          <h3 class="project-title">{{ project.title }}</h3>

          <p class="project-desc">
            {{ project.description }}
          </p>

          <!-- TECH STACK -->
          <div class="tech">
            <strong>Tools & Technologies:</strong>
            <span>{{ project.tech }}</span>
          </div>

        </div>

      </div>

    </div>

  </section>
</template>

<script setup>
import { onMounted } from "vue"

const projects = [
  {
    title: "Vue Portfolio Website",
    description:
      "A modern portfolio site built with Vue.js and Bootstrap showcasing skills, projects, and contact form. Fully responsive and animated.",
    tech: "Vue.js, Bootstrap, HTML, CSS, JavaScript"
  },
  {
    title: "School Management System",
    description:
      "Full-stack school management platform built with React.js, Bootstrap, and Laravel. Contributed to frontend development, project management, and system planning in a two-developer team.",
    tech: "React.js, Bootstrap, Laravel, API Integration"
  },
  {
    title: "Python Voice Automation Assistant",
    description:
      "Desktop automation assistant built with Python that executes voice and text commands, manages files and folders, fetches Wikipedia information, and performs system operations.",
    tech: "Python, Speech Recognition, OS Automation, APIs"
  },
  {
    title: "2D Stickman Fighting Game",
    description:
      "Browser-based multiplayer fighting game with levels, boss battles, and local multiplayer mode on PC and mobile.",
    tech: "HTML, CSS, JavaScript, Game Logic, Canvas"
  },
  {
    title: "AI Lyrics Generator",
    description:
      "AI-powered lyrics generator using OpenRouter API that creates creative song lyrics from prompts with a modern UI.",
    tech: "React.js, TypeScript, OpenRouter API, CSS"
  },
  {
    title: "Music Player UI",
    description:
      "Modern UI design of a music player with responsive layout and smooth animations inspired by modern design systems.",
    tech: "React.js, Bootstrap, UI/UX Design, CSS"
  },
  {
    title: "To-Do App (Vue)",
    description:
      "Feature-rich to-do application with task management, priority tags, due dates, and persistent local storage support.",
    tech: "Vue 3, LocalStorage, JavaScript, CSS"
  }
]

/* optional 3D hover effect */
onMounted(() => {
  const cards = document.querySelectorAll(".project-card")

  cards.forEach((card) => {
    card.addEventListener("mousemove", (e) => {
      const rect = card.getBoundingClientRect()

      const x = e.clientX - rect.left
      const y = e.clientY - rect.top

      const rotateX = -(y / rect.height - 0.5) * 10
      const rotateY = (x / rect.width - 0.5) * 10

      card.style.transform = `
        perspective(1000px)
        rotateX(${rotateX}deg)
        rotateY(${rotateY}deg)
        translateY(-6px)
      `

      card.style.setProperty("--x", `${x}px`)
      card.style.setProperty("--y", `${y}px`)
    })

    card.addEventListener("mouseleave", () => {
      card.style.transform =
        "perspective(1000px) rotateX(0deg) rotateY(0deg)"
    })
  })
})
</script>

<style scoped>
.projects-section {
  background: #0D1321;
  padding: 80px 20px;
  color: #F0EBD8;
}

/* TITLE */
.title {
  text-align: center;
  font-size: 2.8rem;
  font-weight: 800;

  background: linear-gradient(90deg, #F0EBD8, #748CAB);
  -webkit-background-clip: text;
  color: transparent;
}

.subtitle {
  text-align: center;
  margin-bottom: 50px;
  opacity: 0.8;
}

/* GRID */
.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 25px;
}

/* GLASS CARD */
.glass-card {
  position: relative;
  padding: 22px;
  border-radius: 22px;

  background: rgba(255, 255, 255, 0.06);
  backdrop-filter: blur(25px);
  -webkit-backdrop-filter: blur(25px);

  border: 1px solid rgba(255, 255, 255, 0.12);

  box-shadow:
    0 10px 30px rgba(0, 0, 0, 0.25),
    inset 0 1px 1px rgba(255,255,255,0.08);

  transition: all 0.3s ease;
  overflow: hidden;
}

/* CURSOR GLOW */
.glass-card::after {
  content: "";
  position: absolute;
  width: 300px;
  height: 300px;

  background: radial-gradient(circle, rgba(116,140,171,0.3), transparent 70%);

  left: var(--x, 50%);
  top: var(--y, 50%);
  transform: translate(-50%, -50%);

  opacity: 0;
  transition: opacity 0.3s ease;
  pointer-events: none;
}

.glass-card:hover::after {
  opacity: 1;
}

/* TEXT */
.project-title {
  font-size: 1.3rem;
  color: #748CAB;
  margin-bottom: 8px;
}

.project-desc {
  font-size: 0.95rem;
  line-height: 1.6;
  opacity: 0.9;
  margin-bottom: 12px;
}

/* TECH */
.tech {
  font-size: 0.85rem;
  opacity: 0.85;
  line-height: 1.4;
}

.tech strong {
  color: #748CAB;
}

/* RESPONSIVE */
@media (max-width: 768px) {
  .title {
    font-size: 2.2rem;
  }
}
</style>
