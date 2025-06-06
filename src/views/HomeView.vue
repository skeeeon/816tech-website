<template>
  <div>
    <HeroSection />
    <SolutionsSection />
    <IndustriesSection />
    <ApproachSection />
    <AboutSection />
    
    <!-- Enhanced Contact section -->
    <section id="contact" class="section" 
             :style="{ backgroundColor: 'var(--color-primary)', color: 'white' }">
      <div class="container mx-auto px-4 text-center">
        <h2 class="text-3xl md:text-4xl font-bold mb-6 text-white">Ready to Transform Your Operations?</h2>
        <p class="text-lg sm:text-xl mb-8 max-w-2xl mx-auto text-white opacity-90">
          Let's discuss how IoT can solve your business challenges and drive measurable results. 
          Contact us for a free consultation and discover what's possible.
        </p>
        
        <!-- Contact options -->
        <div class="grid grid-cols-1 md:grid-cols-3 gap-8 mb-12 max-w-4xl mx-auto">
          <div v-for="(contact, index) in contactOptions" :key="`contact-${index}`" 
               class="contact-option">
            <div class="contact-icon mb-4">
              <i :class="contact.icon" class="text-3xl text-white"></i>
            </div>
            <h3 class="text-xl font-semibold mb-2 text-white">{{ contact.title }}</h3>
            <p class="text-white opacity-80 mb-4">{{ contact.description }}</p>
            <a :href="contact.href" 
               class="btn bg-white hover:bg-gray-100 text-blue-600 font-medium">
              {{ contact.action }}
            </a>
          </div>
        </div>
        
        <!-- Main CTA -->
        <div class="border-t border-white border-opacity-20 pt-8">
          <button class="btn bg-white hover:bg-gray-100 text-blue-600 font-medium text-lg px-8 py-4">
            <i class="pi pi-calendar mr-2"></i>
            Schedule Your Free Consultation
          </button>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
/**
 * Home page view component for 816tech
 * Complete landing page with all sections
 */

// Import all sections
import HeroSection from '../components/home/HeroSection.vue';
import SolutionsSection from '../components/home/SolutionsSection.vue';
import IndustriesSection from '../components/home/IndustriesSection.vue';
import ApproachSection from '../components/home/ApproachSection.vue';
import AboutSection from '../components/home/AboutSection.vue';

// Contact options for the enhanced contact section
const contactOptions = [
  {
    icon: 'pi pi-phone',
    title: 'Call Us',
    description: 'Speak directly with our team about your IoT needs',
    action: 'Call Now',
    href: 'tel:+18165558324'
  },
  {
    icon: 'pi pi-envelope',
    title: 'Email Us',
    description: 'Send us details about your project for a detailed response',
    action: 'Send Email',
    href: 'mailto:info@816tech.com'
  },
  {
    icon: 'pi pi-calendar',
    title: 'Schedule Meeting',
    description: 'Book a free consultation to discuss your requirements',
    action: 'Book Meeting',
    href: '#'
  }
];
</script>

<style scoped>
.container {
  max-width: 1280px;
}

.contact-option {
  @apply p-6 rounded-lg;
  background-color: rgba(255, 255, 255, 0.1);
  backdrop-filter: blur(10px);
  transition: background-color 0.3s ease;
}

.contact-option:hover {
  background-color: rgba(255, 255, 255, 0.15);
}
</style>

<style scoped>
.container {
  max-width: 1280px;
}
</style>
