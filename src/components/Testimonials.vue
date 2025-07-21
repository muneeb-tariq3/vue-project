<template>
  <section class="testimonials py-5" id="testimonials">
    <div class="container">
      <h2 class="section-title text-center mb-5">Testimonials</h2>
      <div class="row g-4">
        <div
          v-for="(testimonial, index) in testimonials"
          :key="index"
          class="col-md-6 col-lg-4"
        >
          <div
            class="card testimonial-card h-100 fade-in"
            :style="{ animationDelay: `${index * 0.3}s` }"
          >
            <div class="card-body">
              <div class="d-flex align-items-center mb-3">
                <img :src="testimonial.avatar" alt="Avatar" class="testimonial-avatar me-3" />
                <div>
                  <h6 class="mb-0">{{ testimonial.name }}</h6>
                  <small class="text-muted">{{ testimonial.position }}</small>
                </div>
              </div>
              <p class="testimonial-text">“{{ testimonial.feedback }}”</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const testimonials = [
  {
    name: 'Sarah Ahmed',
    position: 'UI/UX Designer at Creatix Studio',
    feedback:
      'Muneeb is a highly dedicated developer. His front-end work is sleek, responsive, and thoughtfully crafted.',
    avatar: 'https://i.pravatar.cc/100?img=47'
  },
  {
    name: 'Fatima Khan',
    position: 'Founder of SoftWings',
    feedback:
      'He delivered a complete eCommerce UI in record time. Very professional and focused on quality.',
    avatar: 'https://i.pravatar.cc/100?img=36'
  },
  {
    name: 'Ahsan Tariq',
    position: 'Marketing Lead at TrendPath',
    feedback:
      'Our landing page looks amazing now! Muneeb knows how to design user-friendly and modern interfaces.',
    avatar: 'https://i.pravatar.cc/100?img=12'
  }
];
</script>

<style scoped>
.testimonials {
  background-color: #1D2D44;
}
.section-title {
  color: #F0EBD8;
  font-weight: bold;
}
.testimonial-card {
  background: rgba(13, 19, 33, 0.6);
  border: 1px solid rgba(116, 140, 171, 0.3);
  backdrop-filter: blur(10px);
  border-radius: 20px;
  padding: 2rem;
  box-shadow: 0 8px 25px rgba(0, 0, 0, 0.2);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  opacity: 0;
  transform: translateY(20px);
  animation: fadeInUp 0.6s ease forwards;
}
.testimonial-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 12px 35px rgba(116, 140, 171, 0.3);
}
.testimonial-card {
  background: rgba(13, 19, 33, 0.9); /* #0D1321 with opacity */
  color: #F0EBD8;
  border: 1px solid rgba(62, 92, 118, 0.3);
  backdrop-filter: blur(8px);
  border-radius: 20px;
  box-shadow: 0 8px 25px rgba(0, 0, 0, 0.2);
  padding: 2rem;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  opacity: 0;
  transform: translateY(20px);
  animation: fadeInUp 0.6s ease forwards;
}
.testimonial-text {
  color: #F0EBD8;
}
.testimonial-author h6 {
  color: #748CAB;
}

.fade-in {
  animation: fadeInUp 0.6s ease forwards;
}
@keyframes fadeInUp {
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
.testimonials {
  background: linear-gradient(100deg, #1D2D44, #3E5C76, #748CAB);
  background-size: cover;
  background-position: center;
  padding-top: 4rem;
  padding-bottom: 4rem;
}
</style>
