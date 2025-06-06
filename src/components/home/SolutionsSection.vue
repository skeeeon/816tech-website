<template>
  <section id="solutions" class="section" 
           :style="{ backgroundColor: 'var(--color-surface-primary)' }">
    <div class="container mx-auto px-4">
      <h2 class="section-title text-center">Solutions That Work</h2>
      <p class="section-subtitle text-center">
        We specialize in implementing solutions that solve real business challenges,
        from initial concept to ongoing support.
      </p>
      
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8 mt-12 md:mt-16">
        <div v-for="(solution, index) in solutions" :key="`solution-${index}`" 
             class="feature-card group">
          <div class="feature-icon mb-6">
            <i :class="solution.icon" 
               :style="{ color: solution.color }"></i>
          </div>
          <h3 class="text-xl font-semibold mb-4" 
              :style="{ color: 'var(--color-content-primary)' }">
            {{ solution.title }}
          </h3>
          <p class="mb-6" 
             :style="{ color: 'var(--color-content-secondary)' }">
            {{ solution.description }}
          </p>
          <ul class="space-y-2">
            <li v-for="(capability, capIndex) in solution.capabilities" 
                :key="`cap-${index}-${capIndex}`"
                class="flex items-start text-sm">
              <i class="pi pi-check mr-2 mt-1 flex-shrink-0" 
                 :style="{ color: 'var(--color-success)' }"></i>
              <span :style="{ color: 'var(--color-content-secondary)' }">
                {{ capability }}
              </span>
            </li>
          </ul>
        </div>
      </div>
      
      <!-- Call to action -->
      <div class="text-center mt-12 md:mt-16">
        <p class="text-lg mb-6" 
           :style="{ color: 'var(--color-content-secondary)' }">
          Ready to transform your operations with IoT?
        </p>
        <button 
          @click="scrollToSection('contact')"
          class="btn btn-primary">
          <i class="pi pi-comments mr-2"></i>
          Discuss Your Project
        </button>
      </div>
    </div>
  </section>
</template>

<script setup>
/**
 * Solutions section component for 816tech
 * Highlights IoT implementation capabilities across different solution types
 */

// IoT solution categories - positioned as implementation services
const solutions = [
  {
    icon: 'pi pi-cog',
    color: '#2563eb', // Primary blue
    title: 'System Integration',
    description: 'Connect disparate systems and create unified IoT ecosystems that work together seamlessly.',
    capabilities: [
      'Legacy system modernization',
      'API development and integration',
      'Real-time data synchronization',
      'Cross-platform compatibility'
    ]
  },
  {
    icon: 'pi pi-chart-line',
    color: '#059669', // Green
    title: 'Data Analytics & Monitoring',
    description: 'Transform raw IoT data into actionable insights with custom dashboards and analytics.',
    capabilities: [
      'Real-time monitoring dashboards',
      'Predictive analytics implementation',
      'Custom reporting solutions',
      'Alert and notification systems'
    ]
  },
  {
    icon: 'pi pi-shield',
    color: '#dc2626', // Red
    title: 'Security & Compliance',
    description: 'Implement robust security measures and ensure compliance with industry standards.',
    capabilities: [
      'End-to-end encryption',
      'Access control and authentication',
      'Compliance documentation',
      'Security audit and testing'
    ]
  },
  {
    icon: 'pi pi-server',
    color: '#7c3aed', // Purple
    title: 'Infrastructure Design',
    description: 'Design and deploy scalable IoT infrastructure that grows with your business needs.',
    capabilities: [
      'Network architecture planning',
      'Edge computing implementation',
      'Cloud integration strategies',
      'Scalability and redundancy'
    ]
  },
  {
    icon: 'pi pi-mobile',
    color: '#ea580c', // Orange
    title: 'Custom Applications',
    description: 'Develop tailored applications and interfaces that match your specific workflows.',
    capabilities: [
      'Mobile app development',
      'Web-based control panels',
      'Custom user interfaces',
      'Workflow automation tools'
    ]
  },
  {
    icon: 'pi pi-wrench',
    color: '#0891b2', // Cyan
    title: 'Ongoing Support',
    description: 'Comprehensive support services to keep your IoT systems running smoothly.',
    capabilities: [
      '24/7 monitoring and support',
      'Preventive maintenance',
      'Performance optimization',
      'Training and documentation'
    ]
  }
];

/**
 * Scroll to specified section
 * @param {string} sectionId - ID of the section to scroll to
 */
const scrollToSection = (sectionId) => {
  const element = document.getElementById(sectionId);
  if (element) {
    setTimeout(() => {
      const headerOffset = 80;
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

.feature-card {
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.feature-card:hover {
  transform: translateY(-3px);
}

.feature-icon {
  font-size: 2.5rem;
}
</style>
