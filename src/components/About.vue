<template>
  <section id="about" class="about">
    <div class="section-header reveal">
      <h2 class="section-title">About</h2>
      <p class="section-subtitle">Curious, reliable, and obsessed with craft.</p>
    </div>
    
    <div class="about-grid">
      <div class="about-card glass reveal">
        <h3>What I do</h3>
        <p>I design and build responsive web apps from database to UI. I enjoy shipping features that feel simple, run fast, and are accessible by default.</p>
        <ul class="about-list">
          <li>Laravel & PHP back-ends</li>
          <li>Modern JavaScript and Vue</li>
          <li>Design, Develop & Deploy systems</li>
        </ul>
      </div>
      
      <div class="about-card glass reveal">
        <h3>How I work</h3>
        <p>I communicate clearly, document decisions, and iterate quickly. I care about maintainability and creating interfaces users actually enjoy.</p>
        
        <div class="work-stats">
          <div class="stat-item glass">
            <span class="stat-title">Fast</span>
            <span class="stat-desc">Performance-minded</span>
          </div>
          <div class="stat-item glass">
            <span class="stat-title">Clean</span>
            <span class="stat-desc">Readable code</span>
          </div>
          <div class="stat-item glass">
            <span class="stat-title">A11y</span>
            <span class="stat-desc">Inclusive UI</span>
          </div>
          <div class="stat-item glass">
            <span class="stat-title">Pragmatic</span>
            <span class="stat-desc">Ship the value</span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.about-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 32px;
  margin-top: 48px;
}

.about-card {
  padding: 40px;
  display: flex;
  flex-direction: column;
  gap: 24px;
}

.about-card h3 {
  font-size: 1.5rem;
  color: var(--primary);
}

.about-card p {
  font-size: 1.1rem;
  opacity: 0.8;
}

.about-list {
  list-style: none;
  display: flex;
  flex-direction: column;
  gap: 12px;
}

.about-list li {
  position: relative;
  padding-left: 24px;
}

.about-list li::before {
  content: '→';
  position: absolute;
  left: 0;
  color: var(--primary);
  font-weight: 700;
}

.work-stats {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 16px;
  margin-top: 12px;
}

.stat-item {
  padding: 16px;
  display: flex;
  flex-direction: column;
  gap: 4px;
  border-radius: 16px;
}

.stat-title {
  font-weight: 700;
  font-size: 1.1rem;
}

.stat-desc {
  font-size: 0.85rem;
  opacity: 0.6;
}

.section-header {
  margin-bottom: 40px;
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
  .about-grid {
    grid-template-columns: 1fr;
  }
}
</style>
