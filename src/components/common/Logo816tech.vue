<template>
  <div class="logo-container" :class="size">
    <!-- 816tech figure-8 diamond logo -->
    <svg xmlns="http://www.w3.org/2000/svg" width="40" height="50" viewBox="0 0 200 250" class="logo-image">
      <!-- Two overlapping squares rotated 45 degrees to create figure-8 -->
      <g transform="translate(100, 125)">
        <!-- Top diamond -->
        <rect x="-45" y="-45" width="90" height="90" 
              fill="none" 
              :stroke="isDarkMode ? '#60a5fa' : '#2563eb'" 
              stroke-width="10" 
              transform="translate(0, -35) rotate(45)" />
        
        <!-- Bottom diamond -->
        <rect x="-45" y="-45" width="90" height="90" 
              fill="none" 
              :stroke="isDarkMode ? '#60a5fa' : '#2563eb'" 
              stroke-width="10" 
              transform="translate(0, 35) rotate(45)" />
      </g>
    </svg>
    
    <div v-if="showText" class="logo-text-container">
      <span class="logo-text" :class="{'sr-only': textHidden}">
        <span class="logo-number">816</span><span class="logo-suffix">tech</span>
      </span>
    </div>
  </div>
</template>

<script setup>
import { computed } from 'vue';
import { useTheme } from '@/composables/useTheme';

// Props definition
const props = defineProps({
  size: {
    type: String,
    default: 'md',
    validator: (value) => ['sm', 'md', 'lg'].includes(value)
  },
  showText: {
    type: Boolean,
    default: true
  },
  textHidden: {
    type: Boolean,
    default: false
  }
});

// Use the theme composable
const { isDarkMode } = useTheme();
</script>

<style scoped>
.logo-container {
  display: inline-flex;
  align-items: center;
  gap: 12px;
}

.logo-image {
  height: 40px;
  width: 32px;
  transition: all 0.3s ease;
}

.logo-text-container {
  display: flex;
  flex-direction: column;
}

.logo-text {
  font-family: 'Inter', sans-serif;
  font-weight: 700;
  font-size: 1.5rem;
  letter-spacing: -0.02em;
  transition: color 0.3s ease;
  color: v-bind('isDarkMode ? "#f8fafc" : "var(--color-primary)"');
  line-height: 1;
}

.logo-number {
  color: v-bind('isDarkMode ? "#3b82f6" : "var(--color-primary)"');
}

.logo-suffix {
  color: v-bind('isDarkMode ? "#94a3b8" : "var(--color-secondary)"');
  font-weight: 500;
}

/* Size variants */
.logo-container.sm .logo-image {
  height: 32px;
  width: 26px;
}

.logo-container.sm .logo-text {
  font-size: 1.25rem;
}

.logo-container.lg .logo-image {
  height: 48px;
  width: 38px;
}

.logo-container.lg .logo-text {
  font-size: 1.75rem;
}

/* Accessibility */
.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  padding: 0;
  margin: -1px;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  white-space: nowrap;
  border-width: 0;
}
</style>
