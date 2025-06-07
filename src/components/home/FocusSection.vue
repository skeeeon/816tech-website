<template>
  <section id="focus" class="py-16 md:py-20"
           :style="{ backgroundColor: 'var(--color-surface-secondary)' }">
    <div class="container mx-auto px-4">
      <div class="text-center mb-10 md:mb-12">
        <h2 class="text-2xl sm:text-3xl md:text-4xl font-bold mb-4"
            :style="{ color: 'var(--color-content-primary)' }">
          Why Choose Open Source with 816tech?
        </h2>
        <p class="text-lg max-w-2xl mx-auto"
           :style="{ color: 'var(--color-content-secondary)' }">
          Enterprise reliability. Fortune 500 capabilities. Small business flexibility.
        </p>
      </div>
      <div class="grid grid-cols-1 md:grid-cols-3 gap-8 md:gap-12">
        <div v-for="(focus, index) in focusAreas" :key="`focus-${index}`" 
             class="text-center group">
          <div class="focus-icon mb-4 transition-transform group-hover:scale-110" 
               :style="{ color: focus.color }">
            <i :class="focus.icon"></i>
          </div>
          <h3 class="text-xl font-bold mb-3" 
              :style="{ color: 'var(--color-content-primary)' }">
            {{ focus.title }}
          </h3>
          <p class="text-base" 
             :style="{ color: 'var(--color-content-secondary)' }">
            {{ focus.description }}
          </p>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
/**
 * Focus section component for 816tech
 * Highlights three key value propositions
 */

// Key focus areas
const focusAreas = [
  {
    icon: 'pi pi-dollar',
    color: '#2563eb',
    title: 'Reduce Costs by 50-80%',
    description: 'Save millions on licensing fees. Our clients typically see ROI within 6-12 months by switching from proprietary to open-source solutions.'
  },
  {
    icon: 'pi pi-unlock',
    color: '#059669',
    title: 'Zero Vendor Lock-in',
    description: 'Own your technology stack completely. Modify, extend, or migrate your systems anytime without vendor restrictions or surprise costs.'
  },
  {
    icon: 'pi pi-map-marker',
    color: '#ea580c',
    title: 'Local Kansas City Team',
    description: 'On-site within hours, not days. As your local partner, we provide immediate support and understand midwest business culture.'
  }
];
</script>

<style scoped>
.container {
  max-width: 1280px;
}

.focus-icon {
  font-size: 3rem;
}

/* Add subtle animation on hover */
.group:hover .focus-icon {
  animation: pulse 2s cubic-bezier(0.4, 0, 0.6, 1) infinite;
}

@keyframes pulse {
  0%, 100% {
    opacity: 1;
  }
  50% {
    opacity: .7;
  }
}
</style>
