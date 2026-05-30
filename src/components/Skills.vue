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
