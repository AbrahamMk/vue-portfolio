<template>
  <nav class="navbar glass">
    <div class="nav-container">
      <div class="logo">
        <span class="dot"></span>
        Abraham
      </div>
      
      <div class="nav-links" :class="{ 'active': mobileMenuOpen }">
        <a href="#about" @click="mobileMenuOpen = false">About</a>
        <a href="#skills" @click="mobileMenuOpen = false">Skills</a>
       
        <a href="#contact" @click="mobileMenuOpen = false">Contact</a>
      </div>

      <div class="nav-actions">
        <button class="theme-toggle" @click="$emit('toggle-theme')" aria-label="Toggle theme">
          <svg v-if="isDark" xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="5"/><line x1="12" y1="1" x2="12" y2="3"/><line x1="12" y1="21" x2="12" y2="23"/><line x1="4.22" y1="4.22" x2="5.64" y2="5.64"/><line x1="18.36" y1="18.36" x2="19.78" y2="19.78"/><line x1="1" y1="12" x2="3" y2="12"/><line x1="21" y1="12" x2="23" y2="12"/><line x1="4.22" y1="19.78" x2="5.64" y2="18.36"/><line x1="18.36" y1="5.64" x2="19.78" y2="4.22"/></svg>
          <svg v-else xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M21 12.79A9 9 0 1 1 11.21 3 7 7 0 0 0 21 12.79z"/></svg>
        </button>
        <button class="mobile-toggle" @click="mobileMenuOpen = !mobileMenuOpen">
          <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><line x1="3" y1="12" x2="21" y2="12"/><line x1="3" y1="6" x2="21" y2="6"/><line x1="3" y1="18" x2="21" y2="18"/></svg>
        </button>
      </div>
    </div>
  </nav>
</template>

<script setup>
import { ref } from 'vue';

defineProps({
  isDark: Boolean
});

defineEmits(['toggle-theme']);

const mobileMenuOpen = ref(false);
</script>

<style scoped>
.navbar {
  position: fixed;
  top: 20px;
  left: 50%;
  transform: translateX(-50%);
  width: 90%;
  max-width: 1200px;
  height: 64px;
  z-index: 1000;
  display: flex;
  align-items: center;
  padding: 0 24px;
}

.nav-container {
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo {
  font-weight: 700;
  font-size: 1.25rem;
  display: flex;
  align-items: center;
  gap: 10px;
}

.dot {
  width: 12px;
  height: 12px;
  background: var(--primary);
  border-radius: 50%;
  box-shadow: 0 0 15px var(--primary);
}

.nav-links {
  display: flex;
  gap: 32px;
}

.nav-links a {
  font-weight: 500;
  font-size: 0.95rem;
  opacity: 0.7;
}

.nav-links a:hover {
  opacity: 1;
  color: var(--primary);
}

.nav-actions {
  display: flex;
  gap: 12px;
  align-items: center;
}

.theme-toggle, .mobile-toggle {
  background: rgba(99, 102, 241, 0.1);
  width: 40px;
  height: 40px;
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  color: var(--primary);
  transition: var(--transition);
}

.theme-toggle:hover {
  background: rgba(99, 102, 241, 0.2);
  transform: scale(1.05);
}

.mobile-toggle {
  display: none;
}

@media (max-width: 768px) {
  .nav-links {
    position: absolute;
    top: 80px;
    left: 0;
    width: 100%;
    background: var(--card-bg-light);
    backdrop-filter: blur(12px);
    flex-direction: column;
    padding: 24px;
    border-radius: 20px;
    border: 1px solid var(--glass-border);
    display: none;
  }

  .dark .nav-links {
    background: var(--card-bg-dark);
  }

  .nav-links.active {
    display: flex;
  }

  .mobile-toggle {
    display: flex;
  }
}
</style>
