<template>
  <Transition name="modal">
    <div v-if="show" class="projects-overlay" @click.self="$emit('close')">
      <div class="projects-modal glass">
        <div class="modal-header">
          <div class="header-text">
            <h2 class="section-title">My Projects</h2>
            <p class="section-subtitle">Real-world solutions and experiments</p>
          </div>
          <button class="close-btn glass" @click="$emit('close')" aria-label="Close">
            <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><line x1="18" y1="6" x2="6" y2="18"></line><line x1="6" y1="6" x2="18" y2="18"></line></svg>
          </button>
        </div>
        
        <div class="projects-grid scroll-container">
          <div v-for="(project, index) in projects" :key="index" class="project-card glass reveal" :style="{ animationDelay: (index * 0.1) + 's' }">
            <div class="project-content">
              <h3>{{ project.title }}</h3>
              <p>{{ project.description }}</p>
              <div class="tags-container">
                <span v-for="tag in project.tags" :key="tag" class="tag">{{ tag }}</span>
              </div>
            </div>
            <a :href="project.link" target="_blank" rel="noopener noreferrer" class="project-btn glass">
              {{ project.buttonText }}
              <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M7 17l9.2-9.2M17 17V7H7"/></svg>
            </a>
          </div>
        </div>
      </div>
    </div>
  </Transition>
</template>

<script setup>
defineProps({
  show: Boolean
});

defineEmits(['close']);

const projects = [
  {
    title: 'Restaurant Management System',
    description: 'A comprehensive system for managing restaurant operations, including orders, inventory, and staff management.',
    tags: ['Laravel', 'Vue', 'Inertia'],
    buttonText: 'View demo',
    link: 'https://restaurant.artseb.studio/customer' 
  },
  {
    title: 'Transport Queue Management System',
    description: 'Efficiently manages transport queues and scheduling to streamline passenger flow and vehicle dispatch.',
    tags: ['Laravel', 'PHP'],
    buttonText: 'View demo',
    link: 'https://la.artseb.studio/passenger'
  },
  {
    title: 'Bill Of Materials Management System',
    description: 'A system for managing bill of materials, including orders, inventory, and products management.',
    tags: ['Laravel', 'PHP'],
    buttonText: 'View demo',
    link: 'https://fms.artseb.studio'
  },
  // Add more projects here
];
</script>

<style scoped>
.projects-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.4);
  backdrop-filter: blur(12px);
  z-index: 2000;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 20px;
}

.projects-modal {
  width: 100%;
  max-width: 1100px;
  max-height: 90vh;
  padding: 40px;
  display: flex;
  flex-direction: column;
  gap: 32px;
  box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.5);
  overflow: hidden;
  border: 1px solid rgba(255, 255, 255, 0.1);
}

.modal-header {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
}

.close-btn {
  width: 48px;
  height: 48px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 50%;
  transition: var(--transition);
  color: var(--text-muted-light);
}

.dark .close-btn {
  color: var(--text-muted-dark);
}

.close-btn:hover {
  background: rgba(239, 68, 68, 0.1);
  color: #ef4444;
  transform: rotate(90deg);
}

.scroll-container {
  overflow-y: auto;
  padding-right: 12px;
  margin-right: -12px;
}

.scroll-container::-webkit-scrollbar {
  width: 6px;
}

.scroll-container::-webkit-scrollbar-track {
  background: transparent;
}

.scroll-container::-webkit-scrollbar-thumb {
  background: rgba(99, 102, 241, 0.2);
  border-radius: 10px;
}

.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
  gap: 24px;
}

.project-card {
  padding: 32px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  gap: 32px;
  transition: var(--transition);
  background: rgba(255, 255, 255, 0.3);
}

.dark .project-card {
  background: rgba(30, 41, 59, 0.3);
}

.project-card:hover {
  transform: translateY(-8px);
  background: rgba(255, 255, 255, 0.5);
  border-color: var(--primary);
  box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1);
}

.dark .project-card:hover {
  background: rgba(30, 41, 59, 0.5);
}

.project-content h3 {
  font-size: 1.5rem;
  margin-bottom: 12px;
  background: linear-gradient(135deg, var(--text-light) 0%, var(--primary) 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.dark .project-content h3 {
  background: linear-gradient(135deg, var(--text-dark) 0%, var(--primary) 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.project-content p {
  font-size: 1rem;
  color: var(--text-muted-light);
  margin-bottom: 24px;
  line-height: 1.6;
}

.dark .project-content p {
  color: var(--text-muted-dark);
}

.tags-container {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
}

.project-btn {
  width: 100%;
  padding: 14px 20px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  font-weight: 600;
  font-size: 0.95rem;
  border-radius: 16px;
  background: rgba(99, 102, 241, 0.05);
  border: 1px solid rgba(99, 102, 241, 0.1);
  color: var(--primary);
  text-decoration: none;
}

.project-btn:hover {
  background: var(--primary);
  color: white;
  border-color: var(--primary);
}

.section-title {
  font-size: 3rem;
  margin-bottom: 8px;
  letter-spacing: -0.04em;
  font-weight: 800;
}

.section-subtitle {
  font-size: 1.25rem;
  color: var(--text-muted-light);
}

.dark .section-subtitle {
  color: var(--text-muted-dark);
}

/* Modal Transitions */
.modal-enter-active,
.modal-leave-active {
  transition: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
}

.modal-enter-from,
.modal-leave-to {
  opacity: 0;
  transform: scale(0.9) translateY(20px);
}

@media (max-width: 640px) {
  .projects-modal {
    padding: 24px;
    height: 100vh;
    max-height: 100vh;
    border-radius: 0;
  }
  
  .section-title {
    font-size: 2rem;
  }
}
</style>
