<template>
  <section class="contact-section py-5" id="contact">
    <div class="container">
      <h2 class="text-center section-title mb-4">Contact Me</h2>
      <p class="text-center text-info-highlight mb-5">
  Have a project in mind or just want to say hello? Let's connect!
</p>
      <div class="row justify-content-center">
        <div class="col-md-8">
          <div class="contact-card p-4 rounded shadow-lg">
            <form @submit.prevent="handleSubmit">
              <div class="mb-3">
                <label class="form-label text-light">Name</label>
                <input type="text" class="form-control" placeholder="Your Name" required />
              </div>
              <div class="mb-3">
                <label class="form-label text-light">Email</label>
                <input type="email" class="form-control" placeholder="Your Email" required />
              </div>
              <div class="mb-3">
                <label class="form-label text-light">Message</label>
                <textarea class="form-control" rows="5" placeholder="Write your message..." required></textarea>
              </div>
              <button type="submit" class="btn custom-btn w-100 mt-3">Send Message</button>
            </form>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
function handleSubmit() {
  alert("Thanks! Your message has been submitted.");
}
</script>

<style scoped>
.contact-section {
  background: linear-gradient(to right, #1D2D44, #3E5C76);
  color: #f0ebd8;
}

.section-title {
  color: #f0ebd8;
  font-weight: bold;
}

.contact-card {
  background: rgba(13, 19, 33, 0.9);
  border: 1px solid rgba(116, 140, 171, 0.2);
  backdrop-filter: blur(8px);
  border-radius: 20px;
}

.form-control {
  background-color: rgba(255, 255, 255, 0.05);
  border: 1px solid #748cab;
  color: #f0ebd8;
}

.form-control::placeholder {
  color: #ccc;
}

.custom-btn {
  background-color: #748cab;
  color: #0d1321;
  border: none;
  font-weight: bold;
  transition: 0.3s;
}

.custom-btn:hover {
  background-color: #3e5c76;
  color: #f0ebd8;
}
.text-info-highlight {
  color: #748CAB;
  font-weight: 500;
}
</style>
