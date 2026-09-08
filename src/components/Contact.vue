<template>
  <section id="contact" class="contact">
    <div class="section-header reveal">
      <h2 class="section-title">Contact</h2>
      <p class="section-subtitle">Have a project in mind? Let's talk.</p>
    </div>
    
    <div class="contact-grid">
      <div class="contact-card glass reveal">
        <h3>Get in touch</h3>
        <p>Whether you have a question, a project proposal, or just want to say hi, feel free to reach out!</p>
        
        <div class="contact-btns">
          <a href="mailto:abrahammekonnen197@gmail.com" class="btn btn-primary">Email me</a>
          <a href="tel:+251984721393" class="btn btn-secondary">Call me</a>
        </div>
      </div>
      
      <div class="contact-card glass reveal">
        <h3>Direct Contact & Socials</h3>

        <div class="contact-details">
          <div class="detail-item">
            <span class="detail-label">Email</span>
            <a href="mailto:abrahammekonnen197@gmail.com" class="detail-value link">abrahammekonnen197@gmail.com</a>
          </div>
          <div class="detail-item">
            <span class="detail-label">Phone</span>
            <span class="detail-value">+251 984 721 393</span>
          </div>
          <div class="detail-item">
            <span class="detail-label">Location</span>
            <span class="detail-value">Addis Ababa, Ethiopia</span>
          </div>
        </div>

        <div class="social-grid">
          <a href="https://x.com/AbrahamMek97781" target="_blank" rel="noopener noreferrer" class="social-item glass">
            <div class="social-icon twitter">X</div>
            <span>Twitter</span>
          </a>
          <a href="https://linkedin.com/in/abraham-mekonnen-9b7917288" target="_blank" rel="noopener noreferrer" class="social-item glass">
            <div class="social-icon linkedin">in</div>
            <span>LinkedIn</span>
          </a>
          <a href="https://github.com/AbrahamMk" target="_blank" rel="noopener noreferrer" class="social-item glass">
            <div class="social-icon github">GH</div>
            <span>GitHub</span>
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
  color: var(--text-muted-light);
}

.dark .contact-card p {
  color: var(--text-muted-dark);
}

.contact-btns {
  display: flex;
  gap: 16px;
  margin-top: 12px;
}

.contact-details {
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.detail-item {
  display: flex;
  flex-direction: column;
}

.detail-label {
  font-size: 0.85rem;
  color: var(--text-muted-light);
  font-weight: 500;
}

.dark .detail-label {
  color: var(--text-muted-dark);
}

.detail-value {
  font-weight: 600;
  font-size: 1rem;
}

.detail-value.link:hover {
  color: var(--primary);
  text-decoration: underline;
}

.social-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 12px;
  margin-top: 12px;
}

.social-item {
  display: flex;
  align-items: center;
  gap: 8px;
  padding: 12px;
  border-radius: 12px;
  transition: var(--transition);
  font-size: 0.9rem;
  font-weight: 500;
}

.social-item:hover {
  background: rgba(99, 102, 241, 0.1);
  transform: translateY(-2px);
}

.social-icon {
  width: 28px;
  height: 28px;
  border-radius: 6px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-weight: 700;
  font-size: 0.75rem;
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

@media (max-width: 768px) {
  .contact-grid {
    grid-template-columns: 1fr;
  }
}
</style>
