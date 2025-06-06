<template>
  <section id="industries" class="section"
           :style="{ backgroundColor: 'var(--color-surface-secondary)' }">
    <div class="container mx-auto px-4">
      <h2 class="section-title text-center">Industries We Serve</h2>
      <p class="section-subtitle text-center">
        Specialized solutions tailored to the unique challenges and opportunities
        across diverse industries.
      </p>
      
      <div class="grid grid-cols-1 lg:grid-cols-2 gap-8 md:gap-12 mt-12 md:mt-16">
        <div v-for="(industry, index) in industries" :key="`industry-${index}`" 
             class="industry-card group">
          <div class="industry-header">
            <div class="industry-icon-container" 
                 :style="{ backgroundColor: industry.color + '20' }">
              <i :class="industry.icon" 
                 :style="{ color: industry.color }" 
                 class="industry-icon"></i>
            </div>
            <div>
              <h3 class="text-2xl font-bold mb-2" 
                  :style="{ color: 'var(--color-content-primary)' }">
                {{ industry.title }}
              </h3>
              <p class="text-base" 
                 :style="{ color: 'var(--color-content-secondary)' }">
                {{ industry.description }}
              </p>
            </div>
          </div>
          
          <div class="industry-solutions mt-6">
            <h4 class="font-semibold mb-4" 
                :style="{ color: 'var(--color-content-primary)' }">
              Key Solutions:
            </h4>
            <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
              <div v-for="(solution, solIndex) in industry.solutions" 
                   :key="`sol-${index}-${solIndex}`"
                   class="solution-item">
                <div class="flex items-start">
                  <i :class="solution.icon" 
                     :style="{ color: industry.color }" 
                     class="mr-3 mt-1 flex-shrink-0"></i>
                  <div>
                    <h5 class="font-medium text-sm mb-1" 
                        :style="{ color: 'var(--color-content-primary)' }">
                      {{ solution.name }}
                    </h5>
                    <p class="text-xs" 
                       :style="{ color: 'var(--color-content-secondary)' }">
                      {{ solution.description }}
                    </p>
                  </div>
                </div>
              </div>
            </div>
          </div>
          
          <!-- Results/Benefits -->
          <div class="industry-benefits mt-6 p-4 rounded-lg" 
               :style="{ backgroundColor: 'var(--color-surface-primary)' }">
            <h4 class="font-semibold mb-3 text-sm" 
                :style="{ color: 'var(--color-content-primary)' }">
              Business Impact:
            </h4>
            <ul class="space-y-2">
              <li v-for="(benefit, benIndex) in industry.benefits" 
                  :key="`ben-${index}-${benIndex}`"
                  class="flex items-start text-sm">
                <i class="pi pi-arrow-right mr-2 mt-1 flex-shrink-0" 
                   :style="{ color: industry.color }"></i>
                <span :style="{ color: 'var(--color-content-secondary)' }">
                  {{ benefit }}
                </span>
              </li>
            </ul>
          </div>
        </div>
      </div>
      
      <!-- Call to action -->
      <div class="text-center mt-12 md:mt-16">
        <div class="max-w-2xl mx-auto">
          <h3 class="text-xl font-semibold mb-4" 
              :style="{ color: 'var(--color-content-primary)' }">
            Don't See Your Industry?
          </h3>
          <p class="text-base mb-6" 
             :style="{ color: 'var(--color-content-secondary)' }">
            We work across many industries and adapt our solutions to meet unique challenges. 
            Contact us to discuss your specific needs.
          </p>
          <button 
            @click="scrollToSection('contact')"
            class="btn btn-primary">
            <i class="pi pi-phone mr-2"></i>
            Let's Talk
          </button>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
/**
 * Industries section component for 816tech
 * Showcases industry-specific IoT solutions and their business impact
 */

// Industry-specific solutions and benefits
const industries = [
  {
    icon: 'pi pi-cog',
    color: '#dc2626', // Red for manufacturing
    title: 'Manufacturing & Industrial',
    description: 'Optimize production efficiency, reduce downtime, and improve quality control.',
    solutions: [
      {
        icon: 'pi pi-chart-line',
        name: 'Asset Tracking',
        description: 'Real-time location and status monitoring'
      },
      {
        icon: 'pi pi-exclamation-triangle',
        name: 'Predictive Maintenance',
        description: 'Prevent equipment failures before they occur'
      },
      {
        icon: 'pi pi-stopwatch',
        name: 'Production Monitoring',
        description: 'Track OEE and identify bottlenecks'
      },
      {
        icon: 'pi pi-shield',
        name: 'Safety Compliance',
        description: 'Automated safety monitoring and reporting'
      }
    ],
    benefits: [
      'Reduce unplanned downtime by 30-50%',
      'Increase overall equipment effectiveness',
      'Improve worker safety and compliance',
      'Optimize inventory and supply chain'
    ]
  },
  {
    icon: 'pi pi-heart',
    color: '#059669', // Green for healthcare
    title: 'Healthcare Facilities',
    description: 'Enhance patient care, streamline operations, and ensure regulatory compliance.',
    solutions: [
      {
        icon: 'pi pi-users',
        name: 'Patient Flow',
        description: 'Optimize patient movement and wait times'
      },
      {
        icon: 'pi pi-thermometer',
        name: 'Environmental Monitoring',
        description: 'Track temperature, humidity, and air quality'
      },
      {
        icon: 'pi pi-map-marker',
        name: 'Equipment Tracking',
        description: 'Locate and manage medical equipment'
      },
      {
        icon: 'pi pi-bell',
        name: 'Alert Systems',
        description: 'Critical event notifications and responses'
      }
    ],
    benefits: [
      'Improve patient satisfaction scores',
      'Reduce equipment search time by 80%',
      'Maintain regulatory compliance',
      'Optimize staff efficiency and utilization'
    ]
  },
  {
    icon: 'pi pi-book',
    color: '#7c3aed', // Purple for education
    title: 'Educational Institutions',
    description: 'Create safer, more efficient campuses while optimizing resource utilization.',
    solutions: [
      {
        icon: 'pi pi-shield',
        name: 'Campus Safety',
        description: 'Integrated security and emergency response'
      },
      {
        icon: 'pi pi-home',
        name: 'Space Utilization',
        description: 'Optimize classroom and facility usage'
      },
      {
        icon: 'pi pi-bolt',
        name: 'Energy Management',
        description: 'Reduce energy costs and environmental impact'
      },
      {
        icon: 'pi pi-wifi',
        name: 'Smart Infrastructure',
        description: 'Connected learning environments'
      }
    ],
    benefits: [
      'Reduce energy costs by 20-30%',
      'Improve campus safety and response times',
      'Optimize space utilization and planning',
      'Enhance student and staff experience'
    ]
  },
  {
    icon: 'pi pi-building',
    color: '#ea580c', // Orange for commercial
    title: 'Commercial Real Estate',
    description: 'Attract tenants, reduce operating costs, and increase property value.',
    solutions: [
      {
        icon: 'pi pi-users',
        name: 'Tenant Services',
        description: 'Enhanced tenant experience and satisfaction'
      },
      {
        icon: 'pi pi-bolt',
        name: 'Smart Building Systems',
        description: 'Automated HVAC, lighting, and controls'
      },
      {
        icon: 'pi pi-car',
        name: 'Parking Management',
        description: 'Optimize parking utilization and revenue'
      },
      {
        icon: 'pi pi-chart-bar',
        name: 'Occupancy Analytics',
        description: 'Data-driven space optimization'
      }
    ],
    benefits: [
      'Increase tenant retention and satisfaction',
      'Reduce operating expenses by 15-25%',
      'Improve property value and marketability',
      'Generate new revenue streams'
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

.industry-card {
  @apply p-6 rounded-lg;
  background-color: var(--color-surface-primary);
  box-shadow: var(--shadow-md);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.industry-card:hover {
  transform: translateY(-3px);
  box-shadow: var(--shadow-lg);
}

.industry-header {
  @apply flex items-start space-x-4;
}

.industry-icon-container {
  @apply p-3 rounded-lg flex-shrink-0;
}

.industry-icon {
  @apply text-2xl;
}

.solution-item {
  @apply p-3 rounded-lg;
  background-color: var(--color-surface-secondary);
  transition: background-color 0.2s ease;
}

.solution-item:hover {
  background-color: var(--color-surface-hover);
}
</style>
