<template>
  <section class="skills-section" id="skills">

    <div class="container">

      <!-- TITLE -->
      <h2 class="title">Professional Skills</h2>
      <p class="subtitle">
        A collection of my technical experience and hands-on development journey over the past two years.
      </p>

      <!-- GRID -->
      <div class="skills-grid">

        <div
          class="glass-card skill-card"
          v-for="(skill, index) in skills"
          :key="index"
        >

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

/* ✅ YOUR ORIGINAL SKILLS ARRAY (UNCHANGED) */
const skills = [
{
  name: 'Personal Info',
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
  summary: 'Developing automation scripts, utilities, and backend solutions using Python.',
  points: [
    'Strong understanding of Python fundamentals',
    'Built automation and data processing scripts',
    'Worked with file handling and API integration',
    'Experienced with virtual environments and package management',
    'Used Python for scripting, problem solving, and development tasks'
  ]
},
{
  name: 'GitHub Actions (CI/CD)',
  summary: 'Automating testing, building, and deployment workflows using GitHub Actions.',
  points: [
    'Created automated CI/CD pipelines',
    'Configured workflow files using YAML',
    'Automated build and deployment processes',
    'Integrated GitHub repositories with deployment platforms',
    'Improved development workflow through automation'
  ]
},
{
  name: 'Netlify & Vercel Deployment',
  summary: 'Deploying and managing modern web applications on cloud hosting platforms.',
  points: [
    'Deployed Vue.js and React applications',
    'Configured custom domains and SSL certificates',
    'Managed environment variables and build settings',
    'Integrated GitHub repositories for automatic deployments',
    'Optimized deployment workflows for production environments'
  ]
},
{
  name: 'Linux',
  summary: 'Working efficiently in Linux environments for development and system administration.',
  points: [
    'Comfortable with Linux command-line operations',
    'Managed files, permissions, and processes',
    'Installed and configured development environments',
    'Worked with package managers and system updates',
    'Used Linux for web development and server-related tasks'
  ]
},
{
  name: 'Networking',
  summary: 'Understanding network fundamentals, protocols, and troubleshooting techniques.',
  points: [
    'Knowledge of TCP/IP networking concepts',
    'Understanding of DNS, DHCP, and routing',
    'Performed basic network troubleshooting',
    'Used networking tools for diagnostics and analysis',
    'Familiar with network security best practices'
  ]
},
{
  name: 'Cyber Security',
  summary: 'Learning cybersecurity concepts, ethical hacking, and security assessment techniques.',
  points: [
    'Understanding of cybersecurity fundamentals',
    'Knowledge of vulnerability assessment concepts',
    'Familiar with penetration testing methodologies',
    'Used security-focused Linux distributions for learning',
    'Practiced security analysis in controlled environments'
  ]
},
{
  name: 'Kali Linux',
  summary: 'Using Kali Linux for cybersecurity learning, testing, and research.',
  points: [
    'Familiar with Kali Linux environment',
    'Worked with security and reconnaissance tools',
    'Performed basic network and system assessments',
    'Practiced ethical hacking concepts in lab environments',
    'Used Linux terminal extensively for security tasks'
  ]
},
{
  name: 'Parrot Security OS',
  summary: 'Exploring security testing and privacy-focused workflows with Parrot OS.',
  points: [
    'Worked with Parrot Security OS tools',
    'Performed security-related learning exercises',
    'Explored privacy and anonymity features',
    'Used penetration testing utilities in lab setups',
    'Configured development and security environments'
  ]
},
{
  name: 'BlackArch Linux',
  summary: 'Exploring advanced security tools and penetration testing environments.',
  points: [
    'Familiar with BlackArch Linux ecosystem',
    'Explored specialized security tool collections',
    'Used command-line based security utilities',
    'Studied penetration testing workflows',
    'Practiced cybersecurity concepts in virtual labs'
  ]
},
{
  name: 'Ubuntu',
  summary: 'Using Ubuntu as a primary development and productivity environment.',
  points: [
    'Installed and configured Ubuntu systems',
    'Managed software using APT package manager',
    'Set up web development environments',
    'Worked with terminal-based workflows',
    'Used Ubuntu for daily development and learning'
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
  -webkit-backdrop-filter: blur(25px);

  border: 1px solid rgba(255, 255, 255, 0.12);

  box-shadow:
    0 10px 30px rgba(0, 0, 0, 0.25),
    inset 0 1px 1px rgba(255,255,255,0.08);

  transition: all 0.3s ease;
  overflow: hidden;
}

.skill-card::after {
  content: "";
  position: absolute;
  width: 280px;
  height: 280px;

  background: radial-gradient(circle, rgba(116,140,171,0.3), transparent 70%);

  left: var(--x, 50%);
  top: var(--y, 50%);
  transform: translate(-50%, -50%);
  opacity: 0;
  transition: 0.3s;
  pointer-events: none;
}

.skill-card:hover::after {
  opacity: 1;
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

.skill-list li {
  margin-bottom: 5px;
}

@media (max-width: 768px) {
  .title {
    font-size: 2.2rem;
  }
}
</style>
