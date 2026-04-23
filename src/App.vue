<script setup>
import HeroSection from './components/sections/HeroSection.vue'
import ProblemSection from './components/sections/ProblemSection.vue'
import SolutionSection from './components/sections/SolutionSection.vue'
import FeaturesSection from './components/sections/FeaturesSection.vue'
import CloudSection from './components/sections/CloudSection.vue'
import ProductPreview from './components/sections/ProductPreview.vue'
import HowItWorks from './components/sections/HowItWorks.vue'
import DownloadCTASection from './components/sections/DownloadCTASection.vue'
import FooterSection from './components/sections/FooterSection.vue'
import StickyDownloadBar from './components/ui/StickyDownloadBar.vue'
</script>

<template>
  <div class="min-h-screen bg-white font-sans">
    <!-- Floating header -->
    <header class="fixed top-0 inset-x-0 z-50 flex items-center justify-between px-6 py-3 bg-green-950/60 backdrop-blur-md border-b border-green-800/30">
      <div class="flex items-center gap-2.5">
        <img src="/favicon.png" alt="Safra na Mão" class="w-8 h-8 rounded-lg" />
        <span class="text-white font-bold text-lg tracking-tight">Safra na Mão</span>
      </div>

      <div class="flex items-center gap-6">
        <nav class="hidden sm:flex items-center gap-5">
          <a href="#features" class="text-sm text-green-200/80 hover:text-white transition-colors">Funcionalidades</a>
        </nav>
        <a
          href="/app/"
          class="inline-flex items-center gap-2 px-5 py-2 bg-green-500 hover:bg-green-400 text-green-950 font-semibold rounded-lg text-sm transition-all duration-200 shadow-md shadow-green-500/20 hover:shadow-green-400/30 hover:-translate-y-0.5"
        >
          <svg xmlns="http://www.w3.org/2000/svg" class="w-4 h-4" viewBox="0 0 20 20" fill="currentColor">
            <path fill-rule="evenodd" d="M3 4.5A1.5 1.5 0 014.5 3h3A1.5 1.5 0 019 4.5v3A1.5 1.5 0 017.5 9h-3A1.5 1.5 0 013 7.5v-3zm6 0A1.5 1.5 0 0110.5 3h3A1.5 1.5 0 0115 4.5v3A1.5 1.5 0 0113.5 9h-3A1.5 1.5 0 019 7.5v-3zM3 10.5A1.5 1.5 0 014.5 9h3a1.5 1.5 0 011.5 1.5v3A1.5 1.5 0 017.5 15h-3A1.5 1.5 0 013 13.5v-3zm6 0a1.5 1.5 0 011.5-1.5h3a1.5 1.5 0 011.5 1.5v3a1.5 1.5 0 01-1.5 1.5h-3a1.5 1.5 0 01-1.5-1.5v-3z" clip-rule="evenodd" />
          </svg>
          Entrar no sistema
        </a>
      </div>
    </header>

    <HeroSection />
    <ProblemSection />
    <SolutionSection />
    <FeaturesSection />
    <CloudSection />
    <ProductPreview />
    <HowItWorks />
    <DownloadCTASection />
    <FooterSection />

    <StickyDownloadBar />
  </div>
</template>
