<script setup>
import HeroSection from './components/sections/HeroSection.vue'
import ProblemSection from './components/sections/ProblemSection.vue'
import SolutionSection from './components/sections/SolutionSection.vue'
import FeaturesSection from './components/sections/FeaturesSection.vue'
import CloudSection from './components/sections/CloudSection.vue'
import ProductPreview from './components/sections/ProductPreview.vue'
import HowItWorks from './components/sections/HowItWorks.vue'
import LeadForm from './components/sections/LeadForm.vue'
import FooterSection from './components/sections/FooterSection.vue'
</script>

<template>
  <div class="min-h-screen bg-white font-sans">
    <HeroSection />
    <ProblemSection />
    <SolutionSection />
    <FeaturesSection />
    <CloudSection />
    <ProductPreview />
    <HowItWorks />
    <LeadForm />
    <FooterSection />
  </div>
</template>
