<template>
  <section id="contact" class="contact">
    <div class="section-header reveal">
      <h2 class="section-title">Contact</h2>
      <p class="section-subtitle">Have a project in mind? Let's talk.</p>
    </div>
    
    <div class="contact-grid">
      <div class="contact-card glass reveal">
        <h3>Get in touch</h3>
        <p>Email is the fastest way to reach me. If you include a short brief and timeline, I can respond quicker.</p>
        
        <div class="contact-btns">
          <a href="mailto:abrahammekonnen197@gmail.com" class="btn btn-primary">Email me</a>
          <button class="btn btn-secondary">Call</button>
        </div>
        
        <div class="contact-info">
          <div class="info-item">
            <span class="info-label">Email</span>
            <span class="info-value">abrahammekonnen197@gmail.com</span>
          </div>
          <div class="info-item">
            <span class="info-label">Location</span>
            <span class="info-value">Addis Ababa, Ethiopia</span>
          </div>
        </div>
      </div>
      
      <div class="contact-card glass reveal">
        <h3>Social</h3>

        <div class="social-grid">
          <a href="#" class="social-item glass">
            <div class="social-icon twitter">X</div>
            <span>Twitter</span>
          </a>
          <a href="#" class="social-item glass">
            <div class="social-icon linkedin">in</div>
            <span>LinkedIn</span>
          </a>
          <a href="#" class="social-item glass">
            <div class="social-icon github">GH</div>
            <span>GitHub</span>
          </a>
          <a href="#" class="social-item glass">
            <div class="social-icon email">@</div>
            <span>Email</span>
          </a>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.contact-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 32px;
  margin-top: 48px;
}

.contact-card {
  padding: 40px;
  display: flex;
  flex-direction: column;
  gap: 24px;
}

.contact-card h3 {
  font-size: 1.5rem;
}

.contact-card p {
  font-size: 1.1rem;
  opacity: 0.8;
}

.contact-btns {
  display: flex;
  gap: 16px;
  margin-bottom: 12px;
}

.contact-info {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 24px;
  margin-top: 12px;
}

.social-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 16px;
}

.social-item {
  display: flex;
  align-items: center;
  gap: 12px;
  padding: 16px;
  border-radius: 16px;
  transition: var(--transition);
}

.social-item:hover {
  background: rgba(99, 102, 241, 0.1);
  transform: scale(1.02);
}

.social-icon {
  width: 32px;
  height: 32px;
  border-radius: 8px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-weight: 700;
  font-size: 0.8rem;
  background: rgba(99, 102, 241, 0.2);
  color: var(--primary);
}

.section-title {
  font-size: 2.5rem;
  margin-bottom: 8px;
}

.section-subtitle {
  font-size: 1.1rem;
  color: var(--text-muted-light);
}

.dark .section-subtitle {
  color: var(--text-muted-dark);
}

.info-label {
  font-size: 0.85rem;
  color: var(--text-muted-light);
  font-weight: 500;
  display: block;
}

.dark .info-label {
  color: var(--text-muted-dark);
}

.info-value {
  font-weight: 600;
}

@media (max-width: 768px) {
  .contact-grid {
    grid-template-columns: 1fr;
  }
}
</style>
