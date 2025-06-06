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
          Modern IoT Solutions,<br>
          <span :style="{ color: 'var(--color-primary)' }">Expertly Implemented</span>
        </h1>
        <p class="text-lg sm:text-xl mb-6 sm:mb-8 max-w-2xl"
           :style="{ color: 'var(--color-content-secondary)' }">
          We design, deploy, and support IoT solutions that solve real business challenges 
          across manufacturing, healthcare, education, and commercial real estate.
        </p>
        
        <!-- Key differentiators -->
        <div class="flex flex-wrap gap-4 mb-8 sm:mb-10">
          <div v-for="(highlight, index) in highlights" :key="`highlight-${index}`" 
               class="flex items-center px-3 py-2 rounded-full text-sm font-medium"
               :style="{ 
                 backgroundColor: isDarkMode ? 'rgba(59, 130, 246, 0.2)' : 'rgba(59, 130, 246, 0.1)',
                 color: 'var(--color-primary)'
               }">
            <i :class="`pi ${highlight.icon} mr-2`"></i>
            {{ highlight.text }}
          </div>
        </div>
        
        <div class="flex flex-col sm:flex-row flex-wrap gap-3 sm:gap-4">
          <button 
            @click="scrollToSection('contact')" 
            class="btn btn-primary"
            aria-label="Discuss your IoT project with 816tech">
            Discuss Your Project
          </button>
          <button 
            @click="scrollToSection('industries')" 
            class="btn btn-outlined"
            aria-label="View 816tech industry solutions">
            <i class="pi pi-building mr-2"></i>
            View Solutions
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
 * Emphasizes implementation expertise and industry solutions
 */

// Use theme composable
const { isDarkMode } = useTheme();

// Key differentiators for 816tech
const highlights = [
  { icon: 'pi-verified', text: '15+ Years Experience' },
  { icon: 'pi-cog', text: 'End-to-End Solutions' },
  { icon: 'pi-users', text: 'Local Kansas City Team' }
];

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
