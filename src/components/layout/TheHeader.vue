<template>
  <header class="sticky top-0 z-30 shadow-sm border-b" 
          :style="{ 
            backgroundColor: 'var(--color-surface-primary)',
            borderColor: 'var(--color-border-primary)'
          }">
    <div class="container mx-auto px-4 py-4 md:py-5 flex items-center justify-between">
      <div class="flex items-center">
        <a href="#" class="flex items-center transition-colors" 
           @click.prevent="scrollToTop"
           aria-label="816tech - Return to top">
          <Logo816tech />
        </a>
      </div>
      <TheNavbar />
    </div>
  </header>
</template>

<script setup>
import TheNavbar from './TheNavbar.vue';
import Logo816tech from '../common/Logo816tech.vue';

/**
 * Main header component for 816tech
 * Contains the logo and main navigation
 */

/**
 * Smooth scroll to top of page
 */
const scrollToTop = () => {
  window.scrollTo({
    top: 0,
    behavior: 'smooth'
  });
};
</script>

<style scoped>
.container {
  max-width: 1280px;
}
</style>
