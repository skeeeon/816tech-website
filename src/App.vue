<template>
  <div class="min-h-screen flex flex-col theme-transition">
    <TheHeader />
    <main class="flex-grow">
      <HomeView />
    </main>
    <TheFooter />
  </div>
</template>

<script setup>
/**
 * Root application component for 816tech
 * Defines the main layout structure of the application
 */
import TheHeader from './components/layout/TheHeader.vue';
import HomeView from './views/HomeView.vue';
import TheFooter from './components/layout/TheFooter.vue';
import { useTheme } from './composables/useTheme';

// Initialize the theme system
const { isDarkMode } = useTheme();
</script>

<style>
/* Global container style */
.container {
  @apply px-4 sm:px-6 mx-auto;
  max-width: 1280px;
}

/* Add smooth scrolling to the entire page */
html {
  scroll-behavior: smooth;
}

/* Improve focus styles for accessibility */
:focus-visible {
  @apply outline-none ring-2 ring-primary-500 ring-offset-2;
  @apply dark:ring-primary-400 dark:ring-offset-slate-800;
}

/* Theme transition for smooth color changes */
.theme-transition {
  transition-property: background-color, border-color, color;
  transition-timing-function: ease;
  transition-duration: 0.3s;
}
</style>
