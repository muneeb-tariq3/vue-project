<template>
  <section class="blog-section py-5" id="blog">
    <div class="container">
      <!-- Title & Intro -->
      <h2 class="text-center section-title mb-4">Latest Blog Posts</h2>
      <p class="text-center text-info-highlight mb-5">
        As a passionate developer, I believe knowledge grows by sharing. Here, I post tutorials, lessons learned,
        and insights from my journey in modern web development — with the hope of inspiring and helping others in the community.
      </p>

      <!-- 🌟 Featured Blog Post -->
      <div class="featured-post mb-5 p-4">
        <h4 class="text-light fw-bold">{{ featuredPost.title }}</h4>
        <small class="text-muted d-block mb-2">{{ featuredPost.date }}</small>
        <p class="text-light">{{ featuredPost.excerpt }}</p>
        <a href="#" class="read-more mt-3 d-inline-block">Read Full Post →</a>
      </div>

      <!-- 📝 Blog Cards Grid -->
      <div class="row g-4">
        <div
          v-for="(post, index) in blogPosts"
          :key="index"
          class="col-md-6 col-lg-4"
        >
          <div class="blog-card p-4 h-100 fade-in" :style="{ animationDelay: `${index * 0.3}s` }">
            <h5 class="blog-title mb-2">{{ post.title }}</h5>
            <small class="text-muted">{{ post.date }}</small>
            <p class="blog-excerpt mt-3">{{ post.excerpt }}</p>
            <a href="#" class="read-more mt-3 d-inline-block">Read More →</a>
          </div>
        </div>
      </div>

      <!-- 🔗 View All Posts Button -->
      <div class="text-center mt-5">
        <a href="#" class="btn custom-btn px-4 py-2">View All Posts</a>
      </div>
    </div>
  </section>
</template>

<script setup>
const featuredPost = {
  title: 'How I Started Web Development at 15',
  date: 'June 16, 2025',
  excerpt:
    'Starting at a young age, I explored the web through HTML, CSS, and JavaScript. Here’s my story, the challenges I faced, and the mindset that helped me grow as a developer...'
}

const blogPosts = [
  {
    title: 'Mastering Vue 3 Composition API',
    date: 'June 15, 2025',
    excerpt:
      'Discover the power of the Composition API in Vue 3 and how it makes your code cleaner and more reusable.'
  },
  {
    title: 'Top 5 Frontend Frameworks in 2025',
    date: 'June 10, 2025',
    excerpt:
      'A quick guide comparing Vue, React, Angular, Svelte, and Solid — which one fits your next project?'
  },
  {
    title: 'Responsive Design Tips with TailwindCSS',
    date: 'June 5, 2025',
    excerpt:
      'Learn how to build responsive layouts easily with TailwindCSS’s utility-first classes.'
  }
]
</script>

<style scoped>
.blog-section {
  background: linear-gradient(to right, #1D2D44, #3E5C76);
  color: #f0ebd8;
}

.section-title {
  color: #f0ebd8;
  font-weight: bold;
}

.text-info-highlight {
  color: #748cab;
}

.featured-post {
  background: rgba(13, 19, 33, 0.9);
  border-left: 5px solid #748cab;
  border-radius: 16px;
  backdrop-filter: blur(8px);
  transition: all 0.3s ease;
}

.featured-post:hover {
  transform: translateY(-5px);
  box-shadow: 0 12px 24px rgba(0, 0, 0, 0.3);
}

.blog-card {
  background-color: rgba(13, 19, 33, 0.9);
  border: 1px solid rgba(116, 140, 171, 0.2);
  border-radius: 20px;
  backdrop-filter: blur(8px);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  color: #f0ebd8;
}

.blog-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
}

.blog-title {
  color: #f0ebd8;
  font-weight: bold;
}

.blog-excerpt {
  font-size: 0.95rem;
  line-height: 1.5;
  color: #dcdcdc;
}

.read-more {
  color: #748cab;
  font-weight: 500;
  text-decoration: none;
  transition: color 0.3s ease;
}

.read-more:hover {
  color: #3e5c76;
}

.custom-btn {
  background-color: #748cab;
  color: #0d1321;
  border: none;
  font-weight: bold;
  border-radius: 25px;
  transition: 0.3s;
}

.custom-btn:hover {
  background-color: #3e5c76;
  color: #f0ebd8;
}

.fade-in {
  opacity: 0;
  transform: translateY(20px);
  animation: fadeInUp 0.6s ease forwards;
}

@keyframes fadeInUp {
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>
