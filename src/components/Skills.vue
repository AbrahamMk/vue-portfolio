<template>
  <section id="skills" class="skills">
    <div class="section-header reveal">
      <h2 class="section-title">Skills</h2>
      <p class="section-subtitle">A toolkit built from real projects.</p>
    </div>
    
    <div class="skills-grid">
      <div v-for="(category, index) in skillCategories" :key="index" class="skill-category glass reveal">
        <h3>{{ category.name }}</h3>
        <div class="tags-container">
          <span v-for="tag in category.tags" :key="tag" class="tag">{{ tag }}</span>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const skillCategories = [
  {
    name: 'Front-end',
    tags: ['HTML', 'CSS', 'JavaScript', 'Accessibility', 'Responsive UI']
  },
  {
    name: 'Back-end',
    tags: ['PHP', 'Laravel', 'REST APIs', 'Auth', 'Testing basics']
  },
  {
    name: 'Workflow',
    tags: ['Git', 'Vite', 'CI-friendly', 'Docs', 'Code review']
  }
];
</script>

<style scoped>
.skills-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 24px;
  margin-top: 48px;
}

.skill-category {
  padding: 32px;
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.skill-category h3 {
  font-size: 1.25rem;
  font-weight: 600;
}

.tags-container {
  display: flex;
  flex-wrap: wrap;
  gap: 12px;
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

@media (max-width: 1024px) {
  .skills-grid {
    grid-template-columns: 1fr 1fr;
  }
}

@media (max-width: 640px) {
  .skills-grid {
    grid-template-columns: 1fr;
  }
}
</style>
