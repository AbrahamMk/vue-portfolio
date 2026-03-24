<template>
  <section id="projects" class="projects">
    <div class="section-header reveal">
      <h2 class="section-title">Projects</h2>
      <p class="section-subtitle">Replace these cards with your real work.</p>
    </div>
    
    <div class="projects-grid">
      <div v-for="(project, index) in projects" :key="index" class="project-card glass reveal">
        <div class="project-content">
          <h3>{{ project.title }}</h3>
          <p>{{ project.description }}</p>
          <div class="tags-container">
            <span v-for="tag in project.tags" :key="tag" class="tag">{{ tag }}</span>
          </div>
        </div>
        <button class="project-btn glass">
          {{ project.buttonText }}
        </button>
      </div>
    </div>
  </section>
</template>

<script setup>
const projects = [
  {
    title: 'Portfolio refresh',
    description: 'Elegant UI with dark mode, smooth navigation, and modern typography.',
    tags: ['Laravel', 'Vite', 'CSS'],
    buttonText: 'Request a demo'
  },
  {
    title: 'Business landing page',
    description: 'Conversion-focused site with performance budgets and SEO-friendly structure.',
    tags: ['HTML', 'CSS', 'Analytics'],
    buttonText: 'View details'
  },
  {
    title: 'Admin dashboard',
    description: 'Clean tables, forms, and validation patterns that scale with the product.',
    tags: ['PHP', 'Auth', 'UX'],
    buttonText: 'See screenshots'
  }
];
</script>

<style scoped>
.projects-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 24px;
  margin-top: 48px;
}

.project-card {
  padding: 32px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  gap: 32px;
  transition: var(--transition);
}

.project-card:hover {
  transform: translateY(-8px);
}

.project-content h3 {
  font-size: 1.25rem;
  margin-bottom: 12px;
}

.project-content p {
  font-size: 0.95rem;
  opacity: 0.8;
  margin-bottom: 24px;
}

.tags-container {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
}

.project-btn {
  width: 100%;
  padding: 12px;
  text-align: left;
  font-weight: 500;
  font-size: 0.9rem;
  border-radius: 12px;
  background: rgba(99, 102, 241, 0.05);
  border: 1px solid rgba(99, 102, 241, 0.1);
  color: var(--text-light);
}

.dark .project-btn {
  color: var(--text-dark);
}

.project-btn:hover {
  background: rgba(99, 102, 241, 0.1);
  border-color: var(--primary);
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

@media (max-width: 1024px) {
  .projects-grid {
    grid-template-columns: 1fr 1fr;
  }
}

@media (max-width: 640px) {
  .projects-grid {
    grid-template-columns: 1fr;
  }
}
</style>
