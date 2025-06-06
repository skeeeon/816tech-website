<template>
  <section 
    class="py-16 sm:py-20 md:py-28 lg:py-32 relative overflow-hidden"
    :style="{ 
      background: `linear-gradient(135deg, ${isDarkMode ? '#0f172a' : '#f8fafc'} 0%, ${isDarkMode ? '#1e293b' : '#e2e8f0'} 100%)`
    }"
  >
    <!-- Subtle tech pattern background -->
    <div class="absolute inset-0 opacity-5">
      <svg width="100%" height="100%" xmlns="http://www.w3.org/2000/svg">
        <defs>
          <pattern id="tech-pattern" x="0" y="0" width="60" height="60" patternUnits="userSpaceOnUse">
            <circle cx="30" cy="30" r="2" :fill="isDarkMode ? '#60a5fa' : '#2563eb'" />
            <circle cx="10" cy="10" r="1" :fill="isDarkMode ? '#60a5fa' : '#2563eb'" />
            <circle cx="50" cy="50" r="1" :fill="isDarkMode ? '#60a5fa' : '#2563eb'" />
            <line x1="30" y1="30" x2="10" y2="10" :stroke="isDarkMode ? '#60a5fa' : '#2563eb'" stroke-width="0.5" />
            <line x1="30" y1="30" x2="50" y2="50" :stroke="isDarkMode ? '#60a5fa' : '#2563eb'" stroke-width="0.5" />
          </pattern>
        </defs>
        <rect width="100%" height="100%" fill="url(#tech-pattern)" />
      </svg>
    </div>
    
    <div class="container mx-auto px-4 relative z-10">
      <div class="max-w-4xl">
        <h1 class="text-3xl sm:text-4xl md:text-5xl lg:text-6xl font-bold mb-4 sm:mb-6 leading-tight"
            :style="{ color: 'var(--color-content-primary)' }">
          Enterprise Technology<br>
          <span :style="{ color: 'var(--color-primary)' }">Built on Open Standards</span>
        </h1>
        <p class="text-lg sm:text-xl mb-6 sm:mb-8 max-w-2xl"
           :style="{ color: 'var(--color-content-secondary)' }">
          Kansas City's trusted partner for infrastructure, integration, and innovation. 
          We architect robust solutions using proven open-source technologies that scale with your business.
        </p>
        
        <div class="flex flex-col sm:flex-row flex-wrap gap-3 sm:gap-4">
          <button 
            @click="scrollToSection('contact')" 
            class="btn btn-primary"
            aria-label="Schedule a consultation with 816tech">
            Schedule Consultation
          </button>
          <button 
            @click="scrollToSection('solutions')" 
            class="btn btn-outlined"
            aria-label="Explore 816tech services">
            <i class="pi pi-th-large mr-2"></i>
            Explore Services
          </button>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { useTheme } from '@/composables/useTheme';

/**
 * Hero section component for 816tech
 * Emphasizes open-source expertise and full technology services
 */

// Use theme composable
const { isDarkMode } = useTheme();

/**
 * Scrolls to the specified section with smooth scrolling
 * @param {string} sectionId - The ID of the section to scroll to
 */
const scrollToSection = (sectionId) => {
  const element = document.getElementById(sectionId);
  if (element) {
    // Add a small delay to ensure any UI updates finish first
    setTimeout(() => {
      const headerOffset = 80; // Account for fixed header
      const elementPosition = element.getBoundingClientRect().top;
      const offsetPosition = elementPosition + window.pageYOffset - headerOffset;
      
      window.scrollTo({
        top: offsetPosition,
        behavior: 'smooth'
      });
    }, 100);
  }
};
</script>

<style scoped>
.container {
  max-width: 1280px;
}
</style>
