<template>
  <section class="contact-section" id="contact">

    <!-- GLASS CARD -->
    <div class="glass-card" v-if="!success">

      <h2>Contact Me</h2>
      <p class="sub">Send me a message — I’ll reply soon.</p>

      <!-- ERROR -->
      <p v-if="error" class="error">{{ error }}</p>

      <form @submit.prevent="openConfirm">

        <!-- HONEYPOT (spam protection) -->
        <input v-model="honeypot" class="hidden-input" autocomplete="off" />

        <!-- NAME -->
        <input v-model="name" type="text" placeholder="Your Name" required />

        <!-- EMAIL -->
        <input v-model="email" type="email" placeholder="Your Email" required />

        <!-- MESSAGE -->
        <textarea
          v-model="message"
          placeholder="Your Message"
          required
          @input="updateSuggestion"
        ></textarea>

        <!-- SMART SUGGESTION -->
        <p v-if="suggestion" class="hint">{{ suggestion }}</p>

        <!-- SUBMIT BUTTON -->
        <button :class="{ loading: loading }" type="submit" :disabled="loading">
          {{ loading ? "Sending..." : "Send Message" }}
        </button>

      </form>
    </div>

    <!-- SUCCESS SCREEN -->
    <div v-if="success" class="success-screen">
      <div class="check">✔</div>
      <h2>Message Sent</h2>
      <p>Thanks! I’ll get back to you soon.</p>
    </div>

    <!-- CONFIRM MODAL -->
    <div v-if="showConfirm" class="modal">
      <div class="modal-box">
        <h3>Confirm Message</h3>

        <p><b>Name:</b> {{ name }}</p>
        <p><b>Email:</b> {{ email }}</p>
        <p><b>Message:</b> {{ message }}</p>

        <div class="actions">
          <button @click="showConfirm = false">Cancel</button>
          <button @click="sendEmail">Send</button>
        </div>
      </div>
    </div>

  </section>
</template>

<script setup>
import { ref } from "vue"
import emailjs from "@emailjs/browser"

/* FORM DATA */
const name = ref("")
const email = ref("")
const message = ref("")
const honeypot = ref("")

/* STATES */
const loading = ref(false)
const success = ref(false)
const showConfirm = ref(false)
const error = ref("")

/* UX SUGGESTION */
const suggestion = ref("")

const startTime = Date.now()

/* SMART SUGGESTIONS */
function updateSuggestion() {
  if (message.value.length < 5) {
    suggestion.value = "Need a website?"
  } else if (message.value.length < 20) {
    suggestion.value = "Looking for redesign?"
  } else {
    suggestion.value = ""
  }
}

/* SPAM PROTECTION */
function isSpam() {
  if (honeypot.value) return true
  if (message.value.length < 10) return true
  if (Date.now() - startTime < 2000) return true
  return false
}

/* OPEN CONFIRM MODAL */
function openConfirm() {
  error.value = ""

  if (!name.value || !email.value || !message.value) {
    error.value = "Please fill all fields"
    return
  }

  if (isSpam()) {
    error.value = "Request blocked"
    return
  }

  showConfirm.value = true
}

/* SEND EMAIL */
async function sendEmail() {
  showConfirm.value = false
  loading.value = true

  try {
    await emailjs.send(
      "service_acmauh3",
      "template_snoqw2a",
      {
        from_name: name.value,
        from_email: email.value,
        message: message.value
      },
      "xFTjC81Y27kS2xSPl"
    )

    success.value = true

    name.value = ""
    email.value = ""
    message.value = ""

  } catch (err) {
    error.value = "Failed to send message"
    console.log(err)
  }

  loading.value = false
}
</script>

<style scoped>
.contact-section {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  background: #0d1321;
  padding: 40px;
}

/* GLASS CARD */
.glass-card {
  width: 100%;
  max-width: 600px;
  padding: 30px;

  background: rgba(255,255,255,0.06);
  backdrop-filter: blur(22px);
  -webkit-backdrop-filter: blur(22px);

  border: 1px solid rgba(255,255,255,0.12);
  border-radius: 20px;

  color: white;
  text-align: center;
}

.sub {
  color: rgba(255,255,255,0.7);
}

/* INPUTS */
input, textarea {
  width: 100%;
  margin-top: 10px;
  padding: 12px;

  background: rgba(255,255,255,0.05);
  border: 1px solid rgba(255,255,255,0.15);

  color: white;
  border-radius: 12px;
  transition: 0.3s;
}

input:focus, textarea:focus {
  outline: none;
  border-color: #748cab;
  box-shadow: 0 0 12px rgba(116,140,171,0.4);
}

.hidden-input {
  display: none;
}

.hint {
  font-size: 0.85rem;
  color: rgba(255,255,255,0.6);
}

/* BUTTON */
button {
  width: 100%;
  margin-top: 15px;
  padding: 12px;

  border-radius: 12px;
  border: none;
  background: rgba(255,255,255,0.08);
  color: white;

  cursor: pointer;
  position: relative;
  overflow: hidden;
}

button:hover {
  background: rgba(255,255,255,0.15);
}

/* loading animation */
button.loading::before {
  content: "";
  position: absolute;
  left: -100%;
  top: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(90deg, #748cab, #3e5c76);
  animation: load 1.2s infinite;
}

@keyframes load {
  0% { left: -100%; }
  100% { left: 100%; }
}

/* SUCCESS */
.success-screen {
  color: white;
  text-align: center;
}

.check {
  font-size: 4rem;
  color: #4ade80;
}

/* MODAL */
.modal {
  position: fixed;
  inset: 0;
  background: rgba(0,0,0,0.5);

  display: flex;
  justify-content: center;
  align-items: center;
}

.modal-box {
  width: 90%;
  max-width: 400px;

  padding: 20px;
  background: rgba(255,255,255,0.08);
  backdrop-filter: blur(20px);

  border-radius: 16px;
  color: white;
}

.actions {
  display: flex;
  gap: 10px;
  margin-top: 15px;
}

.actions button {
  flex: 1;
}

/* RESPONSIVE */
@media (max-width: 768px) {
  .glass-card {
    padding: 20px;
  }
}
</style>
