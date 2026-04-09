<template>
  <div :class="{ 'dark': isDark }">
    <Navbar :isDark="isDark" @toggle-theme="toggleTheme" />
    
    <main>
      <Hero />
      <About />
      <Skills />
    
      <Contact />
    </main>
    
    <Projects :show="showProjects" @close="toggleProjects" />
    <Footer />
  </div>
</template>

<script setup>
import { ref, onMounted, watch, provide } from 'vue';
import Navbar from './components/Navbar.vue';
import Hero from './components/Hero.vue';
import About from './components/About.vue';
import Skills from './components/Skills.vue';

import Contact from './components/Contact.vue';
import Footer from './components/Footer.vue';
import Projects from './components/Projects.vue';

const isDark = ref(false);
const showProjects = ref(false);

const toggleProjects = () => {
  showProjects.value = !showProjects.value;
  if (showProjects.value) {
    document.body.style.overflow = 'hidden';
  } else {
    document.body.style.overflow = '';
  }
};

provide('toggleProjects', toggleProjects);

const toggleTheme = () => {
  isDark.value = !isDark.value;
  localStorage.setItem('theme', isDark.value ? 'dark' : 'light');
  document.body.classList.toggle('dark', isDark.value);
};

onMounted(() => {
  const savedTheme = localStorage.getItem('theme');
  if (savedTheme === 'dark' || (!savedTheme && window.matchMedia('(prefers-color-scheme: dark)').matches)) {
    isDark.value = true;
    document.body.classList.add('dark');
  }
});
</script>

<style>
main {
  padding-top: 100px;
}
</style>
