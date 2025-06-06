<template>
  <section id="approach" class="section"
           :style="{ backgroundColor: 'var(--color-surface-primary)' }">
    <div class="container mx-auto px-4">
      <h2 class="section-title text-center">Our Proven Approach</h2>
      <p class="section-subtitle text-center">
        Every successful IoT implementation follows our structured three-phase methodology,
        ensuring projects are delivered on time, on budget, and exceeding expectations.
      </p>
      
      <!-- Three phase methodology -->
      <div class="grid grid-cols-1 lg:grid-cols-3 gap-8 md:gap-12 mt-12 md:mt-16">
        <div v-for="(phase, index) in phases" :key="`phase-${index}`" 
             class="approach-phase relative">
          <!-- Phase number and connector -->
          <div class="phase-header">
            <div class="phase-number" 
                 :style="{ 
                   backgroundColor: phase.color,
                   color: 'white'
                 }">
              {{ index + 1 }}
            </div>
            <!-- Connector line (hidden on mobile, shown on larger screens) -->
            <div v-if="index < phases.length - 1" 
                 class="phase-connector hidden lg:block"
                 :style="{ backgroundColor: phase.color }"></div>
          </div>
          
          <!-- Phase content -->
          <div class="phase-content">
            <div class="phase-icon mb-4" 
                 :style="{ color: phase.color }">
              <i :class="phase.icon"></i>
            </div>
            <h3 class="text-2xl font-bold mb-4" 
                :style="{ color: 'var(--color-content-primary)' }">
              {{ phase.title }}
            </h3>
            <p class="text-base mb-6" 
               :style="{ color: 'var(--color-content-secondary)' }">
              {{ phase.description }}
            </p>
            
            <!-- Activities list -->
            <div class="phase-activities">
              <h4 class="font-semibold mb-3 text-sm uppercase tracking-wide" 
                  :style="{ color: phase.color }">
                Key Activities
              </h4>
              <ul class="space-y-3">
                <li v-for="(activity, actIndex) in phase.activities" 
                    :key="`act-${index}-${actIndex}`"
                    class="flex items-start">
                  <i class="pi pi-check-circle mr-3 mt-1 flex-shrink-0" 
                     :style="{ color: phase.color }"></i>
                  <span class="text-sm" 
                        :style="{ color: 'var(--color-content-secondary)' }">
                    {{ activity }}
                  </span>
                </li>
              </ul>
            </div>
            
            <!-- Deliverables -->
            <div class="phase-deliverables mt-6 p-4 rounded-lg" 
                 :style="{ backgroundColor: phase.color + '10' }">
              <h4 class="font-semibold mb-2 text-sm" 
                  :style="{ color: 'var(--color-content-primary)' }">
                Deliverables:
              </h4>
              <p class="text-sm" 
                 :style="{ color: 'var(--color-content-secondary)' }">
                {{ phase.deliverables }}
              </p>
            </div>
          </div>
        </div>
      </div>
      
      <!-- Why this approach works -->
      <div class="mt-16 md:mt-20">
        <div class="max-w-4xl mx-auto text-center">
          <h3 class="text-2xl font-bold mb-6" 
              :style="{ color: 'var(--color-content-primary)' }">
            Why Our Approach Works
          </h3>
          <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
            <div v-for="(benefit, index) in approachBenefits" :key="`benefit-${index}`" 
                 class="approach-benefit">
              <div class="benefit-icon mb-4" 
                   :style="{ color: 'var(--color-primary)' }">
                <i :class="benefit.icon"></i>
              </div>
              <h4 class="font-semibold mb-2" 
                  :style="{ color: 'var(--color-content-primary)' }">
                {{ benefit.title }}
              </h4>
              <p class="text-sm" 
                 :style="{ color: 'var(--color-content-secondary)' }">
                {{ benefit.description }}
              </p>
            </div>
          </div>
        </div>
      </div>
      
      <!-- Call to action -->
      <div class="text-center mt-12 md:mt-16">
        <div class="max-w-2xl mx-auto">
          <h3 class="text-xl font-semibold mb-4" 
              :style="{ color: 'var(--color-content-primary)' }">
            Ready to Start Your IoT Journey?
          </h3>
          <p class="text-base mb-6" 
             :style="{ color: 'var(--color-content-secondary)' }">
            Let's begin with a discovery conversation to understand your challenges 
            and explore how IoT can transform your operations.
          </p>
          <button 
            @click="scrollToSection('contact')"
            class="btn btn-primary">
            <i class="pi pi-calendar mr-2"></i>
            Schedule Discovery Call
          </button>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
/**
 * Our Approach section component for 816tech
 * Details the three-phase implementation methodology: Discover, Design, Deploy
 */

// Three-phase methodology
const phases = [
  {
    title: 'Discover',
    icon: 'pi pi-search',
    color: '#2563eb', // Primary blue
    description: 'We start by deeply understanding your business challenges, current systems, and objectives to ensure our solution aligns perfectly with your needs.',
    activities: [
      'Stakeholder interviews and requirements gathering',
      'Current system assessment and gap analysis',
      'Site surveys and technical feasibility studies',
      'ROI analysis and business case development',
      'Risk assessment and mitigation planning'
    ],
    deliverables: 'Comprehensive project plan, technical specifications, timeline, and budget proposal with clear ROI projections.'
  },
  {
    title: 'Design',
    icon: 'pi pi-palette',
    color: '#059669', // Green
    description: 'Our team creates detailed system architecture, user interfaces, and integration plans tailored to your specific requirements and existing infrastructure.',
    activities: [
      'System architecture and network design',
      'User interface and experience design',
      'Integration planning with existing systems',
      'Security framework and compliance review',
      'Testing strategy and acceptance criteria'
    ],
    deliverables: 'Detailed technical designs, architectural diagrams, user mockups, and implementation roadmap with milestones.'
  },
  {
    title: 'Deploy',
    icon: 'pi pi-cog',
    color: '#ea580c', // Orange
    description: 'We implement, test, and launch your IoT solution with comprehensive training and support to ensure smooth adoption and ongoing success.',
    activities: [
      'System installation and configuration',
      'Integration testing and quality assurance',
      'User training and documentation',
      'Go-live support and monitoring',
      'Performance optimization and fine-tuning'
    ],
    deliverables: 'Fully operational IoT system, comprehensive documentation, trained users, and ongoing support plan.'
  }
];

// Benefits of this structured approach
const approachBenefits = [
  {
    icon: 'pi pi-clock',
    title: 'Predictable Timeline',
    description: 'Structured phases with clear milestones ensure projects stay on schedule and meet deadlines.'
  },
  {
    icon: 'pi pi-dollar',
    title: 'Budget Certainty',
    description: 'Thorough planning and fixed-price phases eliminate cost surprises and scope creep.'
  },
  {
    icon: 'pi pi-star',
    title: 'Quality Assurance',
    description: 'Each phase includes testing and validation to ensure high-quality deliverables and user satisfaction.'
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

.approach-phase {
  position: relative;
}

.phase-header {
  display: flex;
  align-items: center;
  margin-bottom: 2rem;
  position: relative;
}

.phase-number {
  width: 60px;
  height: 60px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.5rem;
  font-weight: bold;
  z-index: 2;
  position: relative;
}

.phase-connector {
  position: absolute;
  left: 60px;
  top: 50%;
  width: calc(100vw / 3 - 120px);
  height: 4px;
  transform: translateY(-50%);
  z-index: 1;
}

.phase-content {
  padding-left: 0;
}

.phase-icon {
  font-size: 2.5rem;
}

.approach-benefit {
  text-align: center;
}

.benefit-icon {
  font-size: 2rem;
}

/* Responsive adjustments */
@media (max-width: 1023px) {
  .phase-header {
    justify-content: center;
  }
  
  .phase-content {
    text-align: center;
  }
  
  .phase-activities,
  .phase-deliverables {
    text-align: left;
  }
}
</style>
