<template>
  <section class="contact-section py-5" id="contact">
    <div class="container">
      <h2 class="section-title text-center mb-5">Get In Touch</h2>
      <div class="row justify-content-center">
        <div class="col-md-8">
          <form @submit.prevent="submitForm" class="contact-form p-4 rounded">
            
            <div class="mb-3">
              <label for="name" class="form-label">Name</label>
              <input type="text" v-model="form.name" class="form-control" id="name" placeholder="Your Name" required>
            </div>

            <div class="mb-3">
              <label for="email" class="form-label">Email</label>
              <input type="email" v-model="form.email" class="form-control" id="email" placeholder="Your Email" required>
            </div>

            <div class="mb-3">
              <label for="message" class="form-label">Message</label>
              <textarea v-model="form.message" class="form-control" id="message" rows="5" placeholder="Write your message..." required></textarea>
            </div>

            <button type="submit" class="btn btn-main w-100">Send Message</button>

          </form>

          <p class="form-status text-center mt-3" v-if="status">{{ status }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { reactive, ref } from 'vue'

const form = reactive({
  name: '',
  email: '',
  message: ''
})

const status = ref('')

function submitForm() {
  // Simulate form submission (Lighthouse-friendly)
  status.value = "Thank you! Your message has been sent."
  form.name = ''
  form.email = ''
  form.message = ''
  setTimeout(() => status.value = '', 5000)
}
</script>

<style scoped>
.contact-section {
  background: linear-gradient(135deg, #0f172a, #020617);
  color: #e5e7eb;
}

.section-title {
  font-weight: 700;
  color: #22d3ee;
  animation: fadeInUp 1s ease forwards;
}

/* Form card */
.contact-form {
  background: rgba(255, 255, 255, 0.05);
  border: 1px solid rgba(34, 211, 238, 0.2);
  border-radius: 16px;
  padding: 2rem;
  transition: transform 0.3s ease, border-color 0.3s ease;
}

.contact-form:hover {
  transform: translateY(-4px);
  border-color: #38bdf8;
}

.contact-form .form-control {
  background: rgba(255, 255, 255, 0.05);
  border: 1px solid rgba(148, 163, 184, 0.3);
  color: #cbd5f5;
}

.contact-form .form-control:focus {
  border-color: #22d3ee;
  box-shadow: 0 0 0 0.2rem rgba(34,211,238,0.25);
}

.btn-main {
  background-color: #22d3ee;
  color: #020617;
  font-weight: 600;
  transition: all 0.3s ease;
}

.btn-main:hover {
  background-color: #38bdf8;
  transform: scale(1.05);
}

.form-status {
  color: #22d3ee;
  font-weight: 500;
}

/* Fade In Up Animation */
@keyframes fadeInUp {
  0% { opacity: 0; transform: translateY(30px);}
  100% { opacity: 1; transform: translateY(0);}
}
</style>