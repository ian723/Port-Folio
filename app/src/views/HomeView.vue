<template>
  <div class="bg-[#111827] min-h-screen">
    <!-- Wrap components in Suspense to handle loading -->
     <Suspense>
      <template #default>
        <!-- Wrap all Components inside a single root element -->
         <div>
            <Navbar />
            <HeroSection />
            <ServicesSection />
            <AboutSection />
            <ExperienceAndSkills />
            <LatestProjSection />
            <ContactSection />
            <TestimonialsSection />
            <Footer />
            <BackToTop />
      </div>
    </template>
    <template #fallback>
      <div class="flex justify-center items-center min-h-screen">
          <LoadingSpinner />
      </div>
    </template>
  </Suspense>
  </div>
</template>

<script setup>
 import { defineAsyncComponent } from 'vue';
//Import Components Asynchronously
const Navbar = defineAsyncComponent(()=>import('@/components/Navbar.vue'));
const HeroSection = defineAsyncComponent(()=>import('@/components/HeroSection.vue'));
const ServicesSection = defineAsyncComponent(()=>import('@/components/ServicesSection.vue'));
const AboutSection = defineAsyncComponent(()=>import('@/components/AboutSection.vue'));
const TestimonialsSection = defineAsyncComponent(()=>import('@/components/TestimonialsSection.vue'));
const LatestProjSection = defineAsyncComponent(()=>import('@/components/LatestProjSection.vue'));
const ExperienceAndSkills = defineAsyncComponent(()=>import('@/components/ExperienceAndSkills.vue'));
const ContactSection = defineAsyncComponent(()=>import('@/components/ContactSection.vue'));
const Footer = defineAsyncComponent(()=>import('@/components/Footer.vue'));
const BackToTop = defineAsyncComponent(()=>import('@/components/BackToTop.vue'));
import LoadingSpinner from '../components/LoadingSpinner.vue';
</script>
<style>

*{
  scrollbar-width: thin;
  scrollbar-color: #111827 #f1f1f1;
}
</style>

