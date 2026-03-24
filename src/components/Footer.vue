<template>
  <footer class="footer">
    <div class="footer-content">
      <div class="copyright">
        <strong>Abraham</strong> &copy; {{ new Date().getFullYear() }}
      </div>
      <a href="#" class="back-to-top" @click.prevent="scrollToTop">
        Back to top
      </a>
    </div>
  </footer>
</template>

<script setup>
const scrollToTop = () => {
  window.scrollTo({ top: 0, behavior: 'smooth' });
};
</script>

<style scoped>
.footer {
  padding: 60px 20px;
  border-top: 1px solid var(--glass-border);
  margin-top: 80px;
}

.dark .footer {
  border-top: 1px solid var(--glass-border-dark);
}

.footer-content {
  max-width: 1200px;
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.copyright {
  font-size: 0.95rem;
  opacity: 0.8;
}

.back-to-top {
  font-size: 0.95rem;
  opacity: 0.6;
}

.back-to-top:hover {
  opacity: 1;
  color: var(--primary);
}
</style>
