 <template>
  <section class="about-section" id="about">
    <div class="container">

      <!-- HERO SECTION -->
      <div class="hero-grid">

        <!-- TEXT CARD -->
        <div class="glass-card hero-text">

          <h2 class="title">About Me</h2>

          <p class="desc">
            I’m Muneeb-ur-Rehman, a frontend developer from Pakistan focused on building modern,
            responsive, and high-performance web experiences.
          </p>

          <p class="desc">
            Over the past 2 years, I’ve built real-world projects, improved UI/UX understanding,
            and gained strong practical experience by continuously working on frontend development.
          </p>

          <p class="desc">
            I am currently in Matric (Age 16) and actively growing my development skills
            while working toward professional-level frontend engineering.
          </p>

          <!-- BUTTONS -->
          <div class="btn-group">

            <a
              href="mailto:muneebtariq841@gmail.com"
              class="glass-btn"
            >
              Email Me
            </a>

            <a
              href="https://github.com/muneeb-tariq3"
              target="_blank"
              class="glass-btn"
            >
              GitHub
            </a>

          </div>
        </div>

        <!-- IMAGE CARD (FIXED IMPORT ISSUE) -->
        <div class="glass-card image-card">

          <div class="img-frame">
            <img :src="pic" alt="profile" />
          </div>

          <div class="glow"></div>

        </div>

      </div>

      <!-- STATS -->
      <div class="stats-grid">

        <div class="glass-card stat-card">
          <h3>45+</h3>
          <p>Projects Built</p>
        </div>

        <div class="glass-card stat-card">
          <h3>2+</h3>
          <p>Years Learning</p>
        </div>

        <div class="glass-card stat-card">
          <h3>30+</h3>
          <p>GitHub Repositories</p>
        </div>

      </div>

    </div>
  </section>
</template>

<script setup>
import { onMounted } from "vue"
import pic from "../assets/pic.png"   // ✅ FIXED (NO @ alias issue)

onMounted(() => {
  const cards = document.querySelectorAll(".glass-card")

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
      card.style.transform = `
        perspective(1000px)
        rotateX(0deg)
        rotateY(0deg)
      `
    })
  })
})
</script>

<style scoped>
.about-section {
  background: #0D1321;
  padding: 80px 20px;
  color: #F0EBD8;
}

/* LAYOUT */
.hero-grid {
  display: grid;
  grid-template-columns: 1.2fr 0.8fr;
  gap: 30px;
  align-items: center;
}

/* GLASS EFFECT */
.glass-card {
  position: relative;
  padding: 25px;
  border-radius: 24px;

  background: rgba(255, 255, 255, 0.06);
  backdrop-filter: blur(25px);
  -webkit-backdrop-filter: blur(25px);

  border: 1px solid rgba(255, 255, 255, 0.12);

  box-shadow:
    0 10px 35px rgba(0, 0, 0, 0.3),
    inset 0 1px 1px rgba(255,255,255,0.08);

  transition: all 0.3s ease;
  overflow: hidden;
}

/* CURSOR LIGHT GLOW */
.glass-card::after {
  content: "";
  position: absolute;

  width: 300px;
  height: 300px;

  background: radial-gradient(circle, rgba(116,140,171,0.35), transparent 70%);

  left: var(--x, 50%);
  top: var(--y, 50%);
  transform: translate(-50%, -50%);

  opacity: 0;
  transition: opacity 0.3s ease;
  pointer-events: none;
}

.glass-card:hover::after {
  opacity: 1;
}

/* TITLE */
.title {
  font-size: 2.5rem;
  font-weight: 800;

  background: linear-gradient(90deg, #F0EBD8, #748CAB);
  -webkit-background-clip: text;
  color: transparent;

  margin-bottom: 15px;
}

/* TEXT */
.desc {
  font-size: 1rem;
  line-height: 1.7;
  opacity: 0.9;
  margin-bottom: 12px;
}

/* BUTTONS */
.btn-group {
  display: flex;
  gap: 15px;
  margin-top: 20px;
}

.glass-btn {
  padding: 10px 18px;
  border-radius: 999px;
  text-decoration: none;
  color: #F0EBD8;

  background: rgba(255,255,255,0.08);
  backdrop-filter: blur(15px);

  border: 1px solid rgba(255,255,255,0.15);

  transition: 0.3s;
}

.glass-btn:hover {
  transform: translateY(-3px);
  border-color: #748CAB;
}

/* IMAGE FRAME */
.image-card {
  display: flex;
  justify-content: center;
  align-items: center;
}

.img-frame {
  width: 220px;
  height: 220px;
  border-radius: 50%;

  padding: 10px;

  background: rgba(255,255,255,0.08);
  backdrop-filter: blur(25px);

  border: 2px solid rgba(255,255,255,0.2);

  box-shadow: 0 0 30px rgba(116,140,171,0.3);
}

.img-frame img {
  width: 100%;
  height: 100%;
  border-radius: 50%;
  object-fit: cover;
}

/* STATS */
.stats-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
  margin-top: 40px;
}

.stat-card {
  text-align: center;
}

.stat-card h3 {
  font-size: 2rem;
  color: #748CAB;
}

/* RESPONSIVE */
@media (max-width: 900px) {
  .hero-grid {
    grid-template-columns: 1fr;
  }

  .stats-grid {
    grid-template-columns: 1fr;
  }
}
</style>
