<template>
  <section class="services py-5" id="services">
    <div class="container">
      <h2 class="section-title text-center mb-5">My Services</h2>
      <div class="row g-4">
        <div
          v-for="(service, index) in services"
          :key="index"
          class="col-md-6 col-lg-4"
        >
          <div
            class="card service-card h-100 fade-in"
            :style="{ animationDelay: `${index * 0.2}s` }"
          >
            <div class="card-body text-center">
              <i :class="service.icon" class="service-icon mb-3"></i>
              <h5 class="card-title">{{ service.title }}</h5>
              <ul class="service-points mt-3">
                <li v-for="(point, i) in service.points" :key="i">
                  {{ point }}
                </li>
              </ul>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const services = [
  {
    title: 'Web Development',
    icon: 'fas fa-code',
    points: [
      'Build fast and responsive websites using HTML, CSS, and JS.',
      'Cross-browser and cross-device compatibility.',
      'SEO-friendly and accessible layouts.',
      'Pixel-perfect designs from Figma or XD.',
      'Performance optimized and secure.',
      'Deploy static or dynamic websites.',
      'Ongoing maintenance and updates.',
      'Modern practices using Bootstrap and frameworks.',
      'Intuitive user interface development.',
      'Custom web solutions for all business types.'
    ]
  },
  {
    title: 'UI/UX Design',
    icon: 'fas fa-pencil-ruler',
    points: [
      'Create clean and functional interface designs.',
      'Wireframing, prototyping, and final design delivery.',
      'Focused on user-centered design approach.',
      'Mobile-first and responsive thinking.',
      'Accessibility and modern design standards.',
      'Reusable component-based systems.',
      'Elegant typography and color usage.',
      'Collaborate easily with developers.',
      'Fast iterations using Figma/Adobe XD.',
      'Designs that improve user retention and conversion.'
    ]
  },
  {
    title: 'Front-End Development',
    icon: 'fas fa-laptop-code',
    points: [
      'Vue.js, React, Angular front-end development.',
      'Reusable, modular and clean code.',
      'Single Page Applications with dynamic routing.',
      'Component-driven architecture.',
      'CSS animations, transitions and interactivity.',
      'Responsive layout using Flexbox/Grid.',
      'Optimized JavaScript with ES6+.',
      'REST API and Firebase integration.',
      'Bug fixing and UI improvements.',
      'Use of TailwindCSS and Bootstrap effectively.'
    ]
  }
];
</script>

<style scoped>
.services {
  background-color: #1D2D44;
}
.section-title {
  color: #F0EBD8;
  font-size: 2rem;
}

/* Card style */
.service-card {
  background-color: #0D1321;
  border: 1px solid #3E5C76;
  color: #F0EBD8;
  border-radius: 12px;
  padding: 1.5rem;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}
.service-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 0 12px rgba(116, 140, 171, 0.3);
}

/* Icon */
.service-icon {
  color: #3E5C76;
  font-size: 2.2rem;
}

/* Title */
.card-title {
  font-weight: 600;
  color: #748CAB;
  margin-bottom: 1rem;
  font-size: 1.2rem;
}

/* Bullet points */
.service-points {
  list-style: disc;
  padding-left: 1.2rem;
  font-size: 0.92rem;
  color: #F0EBD8;
}
.service-points li {
  margin-bottom: 8px;
}

/* Animation */
.fade-in {
  opacity: 0;
  transform: translateY(10px);
  animation: fadeUp 0.5s ease-out forwards;
}
@keyframes fadeUp {
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

/* Responsive improvements */
@media (max-width: 768px) {
  .card-title {
    font-size: 1rem;
  }
  .service-icon {
    font-size: 1.6rem;
  }
  .service-points {
    font-size: 0.85rem;
  }
}
</style>
