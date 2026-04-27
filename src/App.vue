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
        <img src="/icon_foreground.png" alt="Safra na Mão" class="w-8 h-8" />
        <span class="text-white font-bold text-lg tracking-tight">Safra na Mão</span>
      </div>

      <div class="flex items-center gap-6">
        <nav class="hidden sm:flex items-center gap-5">
          <a href="#features" class="text-sm text-green-200/80 hover:text-white transition-colors">Funcionalidades</a>
        </nav>
        <div class="flex items-center gap-2">
          <a
            href="/app/"
            class="inline-flex items-center gap-2 px-5 py-2 bg-green-500 hover:bg-green-400 text-green-950 font-semibold rounded-lg text-sm transition-all duration-200 shadow-md shadow-green-500/20 hover:shadow-green-400/30 hover:-translate-y-0.5"
          >
            <svg xmlns="http://www.w3.org/2000/svg" class="w-4 h-4" viewBox="0 0 20 20" fill="currentColor">
              <path fill-rule="evenodd" d="M18 10a8 8 0 11-16 0 8 8 0 0116 0zm-5.5-2.5a2.5 2.5 0 11-5 0 2.5 2.5 0 015 0zM10 12a5.99 5.99 0 00-4.793 2.39A6.483 6.483 0 0010 16.5a6.483 6.483 0 004.793-2.11A5.99 5.99 0 0010 12z" clip-rule="evenodd" />
            </svg>
            <span class="hidden sm:inline">Acessar painel</span>
          </a>
          <a
            href="/webapp/"
            class="inline-flex items-center gap-2 px-4 py-2 border border-green-400/60 text-green-300 hover:bg-green-800/40 hover:text-white font-semibold rounded-lg text-sm transition-all duration-200 hover:-translate-y-0.5"
          >
            <svg xmlns="http://www.w3.org/2000/svg" class="w-4 h-4" viewBox="0 0 20 20" fill="currentColor">
              <path d="M8 16.25a.75.75 0 01.75-.75h2.5a.75.75 0 010 1.5h-2.5a.75.75 0 01-.75-.75z" />
              <path fill-rule="evenodd" d="M4 3a2 2 0 00-2 2v9a2 2 0 002 2h12a2 2 0 002-2V5a2 2 0 00-2-2H4zm12 1.5H4a.5.5 0 00-.5.5v9a.5.5 0 00.5.5h12a.5.5 0 00.5-.5V5a.5.5 0 00-.5-.5z" clip-rule="evenodd" />
            </svg>
            <span class="hidden sm:inline">Abrir app web</span>
          </a>
        </div>
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
