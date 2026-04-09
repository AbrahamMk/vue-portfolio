<script setup>
import { inject } from 'vue';
import profileImg from '../assets/profile.jpg';

const toggleProjects = inject('toggleProjects');
</script>

<template>
  <section id="hero" class="hero">
    <div class="hero-content">
      <div class="hero-text reveal">
        <span class="badge">Web Developer</span>
        <h1>I build clean, fast, delightful web experiences.</h1>
        <p class="subtitle">Full-stack developer focused on modern Laravel apps, accessible UI, and pragmatic engineering.</p>
        
        <div class="hero-btns">
          <button @click="toggleProjects" class="btn btn-primary">View projects</button>
          <a href="#contact" class="btn btn-secondary">Let's work together</a>
        </div>
        
        <div class="social-links">
          <a href="https://x.com/AbrahamMek97781" target="_blank" rel="noopener noreferrer" class="social-tag glass" aria-label="Twitter">
            <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M22 4s-.7 2.1-2 3.4c1.6 10-9.4 17.3-18 11.6 2.2.1 4.4-.6 6-2C3 15.5.5 9.6 3 5c2.2 2.6 5.6 4.1 9 4-.9-4.2 4-6.6 7-3.8 1.1 0 3-1.2 3-1.2z"/></svg>
            Twitter 
          </a>
          <a href="https://linkedin.com/in/abraham-mekonnen-9b7917288" target="_blank" rel="noopener noreferrer" class="social-tag glass" aria-label="LinkedIn">
            <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"/><rect x="2" y="9" width="4" height="12"/><circle cx="4" cy="4" r="2"/></svg>
            LinkedIn
          </a>
          <a href="mailto:abrahammekonnen197@gmail.com" class="social-tag glass" aria-label="Email">
            <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6"/></svg>
            Email
          </a>
        </div>
      </div>
      
      <div class="hero-card-container reveal">
        <div class="profile-card glass">
          <div class="profile-img-container">
            <div class="profile-img-glow"></div>
            <img :src="profileImg" alt="Abraham" class="profile-img">
          </div>
          <div class="profile-info">
            <div class="info-item">
              <span class="info-label">Location</span>
              <span class="info-value">Addis Ababa, Ethiopia</span>
            </div>
            <div class="info-item">
              <span class="info-label">Phone</span>
              <span class="info-value">+251 984 721 393</span>
            </div>
            <div class="info-item">
              <span class="info-label">Email</span>
              <a href="mailto:abrahammekonnen197@gmail.com" class="info-value link">abrahammekonnen197@gmail.com</a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.hero {
  min-height: 80vh;
  display: flex;
  align-items: center;
  position: relative;
}

.hero::before {
  content: '';
  position: absolute;
  top: -100px;
  left: -100px;
  width: 400px;
  height: 400px;
  background: radial-gradient(circle, rgba(99, 102, 241, 0.15) 0%, transparent 70%);
  z-index: -1;
}

.hero-content {
  display: grid;
  grid-template-columns: 1.2fr 0.8fr;
  gap: 60px;
  align-items: center;
  width: 100%;
}

.badge {
  color: var(--primary);
  font-weight: 600;
  font-size: 0.9rem;
  margin-bottom: 20px;
  display: block;
}

h1 {
  font-size: 4rem;
  margin-bottom: 24px;
  letter-spacing: -0.02em;
}

.subtitle {
  font-size: 1.25rem;
  color: var(--text-muted-light);
  margin-bottom: 40px;
  max-width: 600px;
}

.dark .subtitle {
  color: var(--text-muted-dark);
}

.hero-btns {
  display: flex;
  gap: 20px;
  margin-bottom: 60px;
}

.social-links {
  display: flex;
  gap: 16px;
}

.social-tag {
  display: flex;
  align-items: center;
  gap: 8px;
  padding: 8px 16px;
  border-radius: 9999px;
  font-weight: 500;
  font-size: 0.9rem;
  color: var(--text-light);
}

.dark .social-tag {
  color: var(--text-dark);
}

.profile-card {
  padding: 40px;
  display: flex;
  flex-direction: column;
  gap: 32px;
  position: relative;
  overflow: hidden;
}

.profile-img-container {
  position: relative;
  width: 240px;
  height: 240px;
  margin: 0 auto;
}

.profile-img-glow {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 105%;
  height: 105%;
  background: linear-gradient(135deg, #6366f1, #a855f7);
  border-radius: 50%;
  opacity: 0.6;
  filter: blur(15px);
}

.profile-img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-radius: 50%;
  position: relative;
  z-index: 1;
  border: 4px solid white;
}

.dark .profile-img {
  border-color: #1e293b;
}

.profile-info {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.info-item {
  display: flex;
  flex-direction: column;
}

.info-label {
  font-size: 0.85rem;
  color: var(--text-muted-light);
  font-weight: 500;
}

.dark .info-label {
  color: var(--text-muted-dark);
}

.info-value {
  font-weight: 600;
  font-size: 1rem;
}

.info-value.link:hover {
  color: var(--primary);
  text-decoration: underline;
}

@media (max-width: 1024px) {
  .hero-content {
    grid-template-columns: 1fr;
    text-align: center;
  }

  h1 {
    font-size: 3rem;
  }

  .subtitle {
    margin: 0 auto 40px;
  }

  .hero-btns, .social-links {
    justify-content: center;
  }

  .profile-card {
    max-width: 400px;
    margin: 0 auto;
  }
}
</style>
