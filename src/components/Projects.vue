<template>
  <section id="projects" class="projects">
    <div class="section-header reveal">
      <h2 class="section-title">Featured Projects</h2>
      <p class="section-subtitle">Real-world solutions, web applications, and systems.</p>
    </div>

    <div class="projects-grid">
      <div
        v-for="(project, index) in projects"
        :key="index"
        class="project-card glass reveal"
      >
        <div class="card-banner" :style="{ background: project.gradient }">
          <div class="banner-badge">{{ project.category }}</div>
        </div>
        <div class="project-content">
          <h3>{{ project.title }}</h3>
          <p>{{ project.description }}</p>
          <div class="tags-container">
            <span v-for="tag in project.tags" :key="tag" class="tag">{{ tag }}</span>
          </div>
          <div class="project-actions">
            <a
              :href="project.link"
              target="_blank"
              rel="noopener noreferrer"
              class="btn btn-primary btn-sm"
            >
              {{ project.buttonText }}
              <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"/><polyline points="15 3 21 3 21 9"/><line x1="10" y1="14" x2="21" y2="3"/></svg>
            </a>
            <a
              v-if="project.github"
              :href="project.github"
              target="_blank"
              rel="noopener noreferrer"
              class="btn btn-secondary btn-sm"
              aria-label="View source code on GitHub"
            >
              <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M15 22v-4a4 4 0 0 0-1-3.5c3 0 6-2 6-5.5.08-1.25-.27-2.48-1-3.5.28-1.15.28-2.35 0-3.5 0 0-1 0-3 1.5-2.64-.5-5.36-.5-8 0C6 2 5 2 5 2c-.3 1.15-.3 2.35 0 3.5A5.403 5.403 0 0 0 4 9c0 3.5 3 5.5 6 5.5-.39.49-.68 1.05-.85 1.65-.17.6-.22 1.23-.15 1.85v4"/><path d="M9 18c-4.51 2-5-2-7-2"/></svg>
              Code
            </a>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const projects = [
  {
    title: 'Restaurant Management System',
    description: 'A comprehensive system for managing restaurant operations, including online customer ordering, inventory, and staff management.',
    category: 'Full Stack App',
    gradient: 'linear-gradient(135deg, rgba(99, 102, 241, 0.2) 0%, rgba(168, 85, 247, 0.2) 100%)',
    tags: ['Laravel', 'Vue', 'Inertia.js', 'Tailwind CSS'],
    buttonText: 'Live Demo',
    link: 'https://restaurant.artseb.studio/customer',
    github: 'https://github.com/AbrahamMk'
  },
  {
    title: 'Transport Queue Management System',
    description: 'Efficiently manages transport queues and dispatch scheduling to streamline passenger flow and vehicle dispatching.',
    category: 'Web System',
    gradient: 'linear-gradient(135deg, rgba(59, 130, 246, 0.2) 0%, rgba(99, 102, 241, 0.2) 100%)',
    tags: ['Laravel', 'PHP', 'MySQL', 'Bootstrap'],
    buttonText: 'Live Demo',
    link: 'https://la.artseb.studio/passenger',
    github: 'https://github.com/AbrahamMk'
  },
  {
    title: 'Bill Of Materials Management System',
    description: 'An enterprise web application for managing bill of materials, inventory tracking, orders, and manufacturing products.',
    category: 'Enterprise Software',
    gradient: 'linear-gradient(135deg, rgba(168, 85, 247, 0.2) 0%, rgba(236, 72, 153, 0.2) 100%)',
    tags: ['Laravel', 'PHP', 'REST API', 'MySQL'],
    buttonText: 'Live Demo',
    link: 'https://fms.artseb.studio',
    github: 'https://github.com/AbrahamMk'
  }
];
</script>

<style scoped>
.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  gap: 32px;
  margin-top: 48px;
}

.project-card {
  display: flex;
  flex-direction: column;
  overflow: hidden;
  transition: var(--transition);
}

.project-card:hover {
  transform: translateY(-6px);
  border-color: var(--primary);
  box-shadow: 0 20px 25px -5px rgba(99, 102, 241, 0.15);
}

.card-banner {
  height: 140px;
  padding: 20px;
  display: flex;
  align-items: flex-start;
  justify-content: flex-end;
  border-bottom: 1px solid var(--glass-border);
  position: relative;
}

.dark .card-banner {
  border-bottom-color: var(--glass-border-dark);
}

.banner-badge {
  font-size: 0.75rem;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 0.05em;
  padding: 6px 12px;
  border-radius: 9999px;
  background: rgba(255, 255, 255, 0.8);
  color: var(--text-light);
  backdrop-filter: blur(8px);
}

.dark .banner-badge {
  background: rgba(15, 23, 42, 0.8);
  color: var(--text-dark);
}

.project-content {
  padding: 28px;
  display: flex;
  flex-direction: column;
  flex: 1;
}

.project-content h3 {
  font-size: 1.35rem;
  margin-bottom: 12px;
}

.project-content p {
  font-size: 0.95rem;
  color: var(--text-muted-light);
  margin-bottom: 20px;
  line-height: 1.6;
  flex: 1;
}

.dark .project-content p {
  color: var(--text-muted-dark);
}

.tags-container {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
  margin-bottom: 24px;
}

.project-actions {
  display: flex;
  gap: 12px;
  align-items: center;
}

.btn-sm {
  padding: 8px 16px;
  font-size: 0.875rem;
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
  .projects-grid {
    grid-template-columns: 1fr;
  }
}
</style>
