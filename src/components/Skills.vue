<template>
  <section class="skills-resume py-5" id="skills">
    <div class="container">
      <h2 class="section-title text-center mb-5 text-light">Professional Skills</h2>
      <div class="row gy-4">
        <div class="col-md-6" v-for="(skill, index) in skills" :key="index">
          <div class="resume-skill p-4 rounded">
            <h4 class="skill-title">{{ skill.name }}</h4>
            <p class="skill-summary">{{ skill.summary }}</p>
            <ul class="skill-details">
              <li v-for="(point, idx) in skill.points" :key="idx">{{ point }}</li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
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
  }
]
</script>

<style scoped>
.skills-resume {
  background-color: #0D1321;
}

.resume-skill {
  background-color: #1D2D44;
  color: #F0EBD8;
  border: 1px solid #3E5C76;
}

.skill-title {
  font-size: 1.5rem;
  color: #748CAB;
  font-weight: bold;
}

.skill-summary {
  font-style: italic;
  font-size: 0.95rem;
  margin-bottom: 0.5rem;
}

.skill-details {
  padding-left: 1.2rem;
  list-style-type: disc;
  margin: 0;
}

.skill-details li {
  margin-bottom: 0.4rem;
}
</style>
