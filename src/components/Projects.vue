<template>
  <section class="projects py-5" id="projects">
    <div class="container">
      <h2 class="section-title text-center text-light mb-5">Projects</h2>
      <div class="row gy-4">
        <div
          class="col-md-6 col-lg-4"
          v-for="(project, index) in projects"
          :key="index"
        >
          <div class="card h-100 project-card">
            <div class="card-body d-flex flex-column">
              <h5 class="card-title">{{ project.title }}</h5>
              <p class="card-text flex-grow-1">{{ project.description }}</p>
              <a
                :href="project.link"
                target="_blank"
                class="btn btn-outline-light mt-auto"
              >
                View Project
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const projects = [
  {
    title: "Vue Portfolio Website",
    description:
      "A modern portfolio site built with Vue.js and Bootstrap showcasing skills, projects, and contact form. Fully responsive and animated.",
    link: "#"
  },{
  title: "School Management System",
  description:
    "Full-stack school management platform built with React.js, Bootstrap, and Laravel. Contributed to frontend development, project management, and system planning in a two-developer team.",
  link: "#"
},
{
  title: "Python Voice Automation Assistant",
  description:
    "Desktop automation assistant built with Python that executes voice and text commands, manages files and folders, fetches Wikipedia information, and performs system operations on Windows and Linux Enviornments.",
  link: "#"
},
{
  title: "2D Stickman Fighting Game",
  description:
    "Browser-based multiplayer fighting game developed using HTML, CSS, and JavaScript. Features 10 levels, boss battles, single-player mode, and local 2-player gameplay on PC and mobile.",
  link: "#"
},
{
  title: "AI Lyrics Generator",
  description:
    "AI-powered lyrics generation web application built with React.js, TypeScript, and OpenRouter API. Generates creative song lyrics from user prompts through a responsive and modern interface.",
  link: "#"
},
  {
    title: "Music Player UI",
    description:
      "Frontend UI of a music player designed by Stich and built using React.js and Bootstrap. Includes responsive layout and animations.",
    link: "#"
  },
  {
    title: "To-Do App (Vue)",
    description:
      "Feature-rich to-do app built in Vue with light/dark mode, due dates, priority tags, and persistent data using localStorage.",
    link: "#"
  },
  
];

</script>

<style scoped>
.projects {
  background-color: #1D2D44;
}

.project-card {
  background-color: #0D1321;
  color: #F0EBD8;
  border: 1px solid #3E5C76;
  transition: transform 0.3s ease;
}

.project-card:hover {
  transform: translateY(-5px);
}

.card-title {
  color: #748CAB;
  font-weight: bold;
}.projects {
  background-color: #1D2D44;
  perspective: 1000px;
}

.project-card {
  background-color: #0D1321;
  color: #F0EBD8;
  border: 1px solid #3E5C76;
  transition: transform 0.4s ease, box-shadow 0.4s ease;
  transform-style: preserve-3d;
  will-change: transform;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
}

.project-card:hover {
  transform: rotateY(8deg) rotateX(4deg) scale(1.02);
  box-shadow: 0 20px 35px rgba(0, 0, 0, 0.3);
}

.card-title {
  color: #748CAB;
  font-weight: bold;
}

</style>
