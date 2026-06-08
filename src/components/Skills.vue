<template>
  <section class="skills-section" id="skills">

    <div class="container">

      <h2 class="title">Professional Skills</h2>
      <p class="subtitle">
        A collection of my technical experience and hands-on development journey over the past two years.
      </p>

      <div class="skills-grid">

        <div
          class="glass-card skill-card"
          v-for="(skill, index) in skills"
          :key="index"
        >

          <!-- ⭐ ICON ADDED -->
          <div class="icon-box">
            <i :class="skill.icon"></i>
          </div>

          <h3 class="skill-title">{{ skill.name }}</h3>
          <p class="skill-summary">{{ skill.summary }}</p>

          <ul class="skill-list">
            <li v-for="(point, i) in skill.points" :key="i">
              {{ point }}
            </li>
          </ul>

        </div>

      </div>

    </div>

  </section>
</template>

<script setup>
import { onMounted } from "vue"

/* ONLY ICON ADDED IN DATA (everything else unchanged) */
const skills = [
{
  name: 'Personal Info',
  icon: 'bi bi-person-circle',
  summary: 'Basic personal details for contact and identification.',
  points: [
    'Full Name: Muneeb-ur-Rehman',
    'Age: 15',
    'Country: Pakistan',
    'Phone: +92 300 6657269',
    'Email: your@email.com'
  ]
},
{
  name: 'Vue.js',
  icon: 'bi bi-box',
  summary: 'Building fast and dynamic front-end apps using Vue 3.',
  points: [
    'Proficient in Composition & Options API',
    'Created reusable and modular components',
    'Used Vue Router and state tools like Pinia',
    'Experienced with transitions and conditional rendering',
    'Built full Vue.js projects with routing and animation'
  ]
},
{
  name: 'Tailwind CSS',
  icon: 'bi bi-palette',
  summary: 'Rapid styling using utility-first classes for responsive design.',
  points: [
    'Custom themes and responsive layouts',
    'Used with Vue & React for modern UI',
    'Tailored configs for design systems',
    'Built pixel-perfect UIs quickly',
    'Good grasp of Flex/Grid using Tailwind'
  ]
},
{
  name: 'JavaScript (ES6+)',
  icon: 'bi bi-braces',
  summary: 'Core language for web development and interaction.',
  points: [
    'Used modern JS: ES6+, async/await, arrow functions',
    'DOM manipulation, API requests, and event handling',
    'Clear understanding of scoping and hoisting',
    'Built interactive UIs and data-based features',
    'Comfortable debugging and optimizing scripts'
  ]
},
{
  name: 'React',
  icon: 'bi bi-react',
  summary: 'Component-based development with reusable logic.',
  points: [
    'Built SPAs with React Router and Hooks',
    'Used functional components and props',
    'Styled using CSS Modules and Bootstrap',
    'Managed local state and forms',
    'Integrated APIs and third-party libraries'
  ]
},
{
  name: 'Angular 20',
  icon: 'bi bi-code-slash',
  summary: 'Developed structured apps with TypeScript & RxJS.',
  points: [
    'Used CLI for scaffolding and lazy loading',
    'Created services, modules, and routing guards',
    'Two-way binding with forms and inputs',
    'Handled Observables and HttpClient',
    'Built enterprise-level modules and features'
  ]
},
{
  name: 'Bootstrap 5',
  icon: 'bi bi-bootstrap',
  summary: 'Created consistent and responsive UIs.',
  points: [
    'Grid system, spacing, utility-first styling',
    'Used navbars, cards, modals, carousels',
    'Quick prototypes and real-world pages',
    'Customized components with SCSS variables',
    'Perfect for landing pages and admin panels'
  ]
},
{
  name: 'HTML5',
  icon: 'bi bi-filetype-html',
  summary: 'Foundation of all modern web pages and apps.',
  points: [
    'Structured semantic elements for accessibility',
    'Handled form controls and validations',
    'Integrated audio, video, and media tags',
    'Used with SEO and responsive techniques',
    'Built layout wireframes with divs and sections'
  ]
},
{
  name: 'CSS3',
  icon: 'bi bi-filetype-css',
  summary: 'Styling web pages with modern effects and layouts.',
  points: [
    'Used Flexbox and Grid for responsive layouts',
    'Created animations and transitions',
    'Applied custom variables and media queries',
    'Used pseudo-selectors and layering techniques',
    'Styled web forms, buttons, and modals'
  ]
},
{
  name: 'Git & GitHub',
  icon: 'bi bi-git',
  summary: 'Version control and collaborative development.',
  points: [
    'Created and maintained personal repositories',
    'Used branching and pull requests effectively',
    'Collaborated on multi-dev projects',
    'Managed commits and resolved conflicts',
    'Deployed apps via GitHub Pages'
  ]
},
{
  name: 'Python',
  icon: 'bi bi-cpu',
  summary: 'Developing automation scripts and backend solutions.',
  points: [
    'Strong understanding of Python fundamentals',
    'Built automation and data processing scripts',
    'Worked with file handling and API integration',
    'Used virtual environments and package management',
    'Problem solving and scripting tasks'
  ]
},
{
  name: 'Linux',
  icon: 'bi bi-terminal',
  summary: 'Working in Linux environments for development.',
  points: [
    'Command-line operations',
    'File and process management',
    'Installed development tools',
    'Used package managers',
    'Development workflows on Ubuntu'
  ]
},
{
  name: 'Cyber Security',
  icon: 'bi bi-shield-lock',
  summary: 'Learning cybersecurity concepts and testing.',
  points: [
    'Security fundamentals',
    'Vulnerability concepts',
    'Penetration testing basics',
    'Security tools exposure',
    'Lab-based practice'
  ]
}

]

onMounted(() => {
  const cards = document.querySelectorAll(".skill-card")

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
.skills-section {
  background: #0D1321;
  padding: 80px 20px;
  color: #F0EBD8;
}

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

.skills-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 25px;
}

.skill-card {
  position: relative;
  padding: 22px;
  border-radius: 22px;
  background: rgba(255, 255, 255, 0.06);
  backdrop-filter: blur(25px);
  border: 1px solid rgba(255, 255, 255, 0.12);
  transition: all 0.3s ease;
  overflow: hidden;
}

/* ⭐ ICON STYLE */
.icon-box {
  font-size: 1.8rem;
  margin-bottom: 10px;
  color: #748CAB;
}

.skill-title {
  font-size: 1.4rem;
  color: #748CAB;
  margin-bottom: 6px;
}

.skill-summary {
  font-size: 0.9rem;
  opacity: 0.85;
  margin-bottom: 10px;
}

.skill-list {
  padding-left: 18px;
  font-size: 0.9rem;
  line-height: 1.6;
}
</style>
