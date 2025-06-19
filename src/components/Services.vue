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
            :style="{ animationDelay: `${index * 0.3}s` }"
          >
            <div class="card-body">
              <div class="text-center mb-3">
                <i :class="service.icon" class="service-icon"></i>
              </div>
              <h5 class="card-title text-center">{{ service.title }}</h5>
              <ul class="service-points">
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
/* Section styling */
.services {
  background-color: #1D2D44;
}
.section-title {
  color: #F0EBD8;
}

/* Card base style */
.service-card {
  background-color: #0D1321;
  border: 1px solid #3E5C76;
  color: #F0EBD8;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  border-radius: 12px;
  overflow: hidden;
  position: relative;
  padding-bottom: 1rem;
}

/* Hover effect */
.service-card:hover {
  transform: translateY(-6px);
  box-shadow: 0 0 20px rgba(116, 140, 171, 0.3);
}

/* Icon & Title */
.service-icon {
  color: #3E5C76;
  font-size: 2rem;
}
.card-title {
  color: #748CAB;
  font-weight: 600;
  margin-bottom: 1rem;
}

/* Description (points) appear on hover */
.service-points {
  max-height: 0;
  overflow: hidden;
  transition: max-height 0.5s ease;
  padding-left: 1.2rem;
  list-style-type: disc;
  font-size: 0.9rem;
}
.service-card:hover .service-points {
  max-height: 300px;
}
.service-points li {
  color: #F0EBD8;
  margin-bottom: 6px;
}

/* Fade-in animation */
.fade-in {
  opacity: 0;
  transform: translateY(20px);
  animation: fadeUp 0.6s ease forwards;
}

@keyframes fadeUp {
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
.service-card {
  background-color: #0D1321;
  border: 1px solid #3E5C76;
  color: #F0EBD8;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  border-radius: 12px;
  overflow: hidden;
  position: relative;
  padding-bottom: 1rem;
  height: 400px; /* 🧱 Fixed height */
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
}

/* Keep this hidden content within the card */
.service-points {
  max-height: 160px; /* fixed inner scrollable area */
  overflow-y: auto;
  padding-left: 1.2rem;
  list-style-type: disc;
  font-size: 0.9rem;
  transition: none;
}

/* Optional: improve scrollbar styling */
.service-points::-webkit-scrollbar {
  width: 5px;
}
.service-points::-webkit-scrollbar-thumb {
  background: #3E5C76;
  border-radius: 10px;
}

</style>
