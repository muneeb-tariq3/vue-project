<template>
  <section class="contact-section" id="contact">

    <div class="container">

      <!-- HEADER -->
      <h2 class="title">Contact Me</h2>
      <p class="subtitle">
        Have a project in mind or just want to connect? Let’s build something amazing together.
      </p>

      <!-- GLASS CARD -->
      <div class="glass-card contact-card">

        <form @submit.prevent="handleSubmit">

          <!-- NAME -->
          <div class="input-box">
            <label>Name</label>
            <input type="text" placeholder="Your Name" required />
          </div>

          <!-- EMAIL -->
          <div class="input-box">
            <label>Email</label>
            <input type="email" placeholder="Your Email" required />
          </div>

          <!-- MESSAGE -->
          <div class="input-box">
            <label>Message</label>
            <textarea rows="5" placeholder="Write your message..." required></textarea>
          </div>

          <!-- BUTTON -->
          <button type="submit" class="send-btn">
            Send Message
          </button>

        </form>

      </div>

    </div>

  </section>
</template>

<script setup>
function handleSubmit() {
  alert("Thanks! Your message has been submitted.")
}
</script>

<style scoped>
.contact-section {
  background: #0D1321;
  padding: 80px 20px;
  color: #F0EBD8;
  position: relative;
  overflow: hidden;
}

/* floating glow blobs (Apple style background depth) */
.contact-section::before,
.contact-section::after {
  content: "";
  position: absolute;
  width: 300px;
  height: 300px;
  filter: blur(120px);
  z-index: 0;
}

.contact-section::before {
  background: #3E5C76;
  top: -80px;
  left: -80px;
  opacity: 0.4;
}

.contact-section::after {
  background: #748CAB;
  bottom: -80px;
  right: -80px;
  opacity: 0.3;
}

/* TITLE */
.title {
  text-align: center;
  font-size: 2.8rem;
  font-weight: 800;

  background: linear-gradient(90deg, #F0EBD8, #748CAB);
  -webkit-background-clip: text;
  color: transparent;
  position: relative;
  z-index: 2;
}

.subtitle {
  text-align: center;
  margin-bottom: 50px;
  opacity: 0.8;
  position: relative;
  z-index: 2;
}

/* GLASS CARD */
.glass-card {
  position: relative;
  z-index: 2;

  max-width: 700px;
  margin: auto;
  padding: 30px;

  background: rgba(255, 255, 255, 0.06);
  backdrop-filter: blur(25px);
  -webkit-backdrop-filter: blur(25px);

  border: 1px solid rgba(255, 255, 255, 0.12);
  border-radius: 24px;

  box-shadow:
    0 20px 50px rgba(0, 0, 0, 0.35),
    inset 0 1px 1px rgba(255,255,255,0.08);

  transition: transform 0.3s ease;
}

/* 3D HOVER */
.glass-card:hover {
  transform: perspective(1000px) rotateX(2deg) rotateY(2deg);
}

/* INPUT BOX */
.input-box {
  margin-bottom: 18px;
}

label {
  display: block;
  font-size: 0.9rem;
  margin-bottom: 6px;
  color: #748CAB;
}

/* INPUTS */
input,
textarea {
  width: 100%;
  padding: 12px 14px;

  border-radius: 12px;
  border: 1px solid rgba(116,140,171,0.4);

  background: rgba(255,255,255,0.05);
  color: #F0EBD8;

  outline: none;

  transition: 0.3s;
  backdrop-filter: blur(10px);
}

/* focus glow */
input:focus,
textarea:focus {
  border-color: #748CAB;
  box-shadow: 0 0 15px rgba(116,140,171,0.3);
  transform: translateY(-2px);
}

/* BUTTON */
.send-btn {
  width: 100%;
  padding: 12px;

  margin-top: 10px;

  border: none;
  border-radius: 14px;

  background: linear-gradient(90deg, #748CAB, #3E5C76);
  color: #0D1321;

  font-weight: bold;
  cursor: pointer;

  transition: 0.3s;
}

.send-btn:hover {
  transform: translateY(-3px);
  box-shadow: 0 10px 25px rgba(116,140,171,0.3);
}

/* RESPONSIVE */
@media (max-width: 768px) {
  .title {
    font-size: 2.2rem;
  }

  .glass-card {
    padding: 20px;
  }
}
</style>
