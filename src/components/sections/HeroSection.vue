<script setup>
import { Motion } from 'motion-v'
import PhoneMockup from '../ui/PhoneMockup.vue'
import { DevicePhoneMobileIcon } from '@heroicons/vue/24/outline'
</script>

<template>
  <section class="relative min-h-screen flex items-center overflow-hidden bg-gradient-to-br from-green-900 via-green-800 to-green-950">
    <!-- Decorative blobs -->
    <div class="absolute inset-0 overflow-hidden pointer-events-none">
      <div class="absolute -top-40 -right-40 w-[500px] h-[500px] bg-green-600/20 rounded-full blur-3xl" />
      <div class="absolute -bottom-20 -left-40 w-[600px] h-[600px] bg-green-500/10 rounded-full blur-3xl" />
    </div>

    <div class="relative z-10 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-20 w-full">
      <div class="grid lg:grid-cols-2 gap-12 lg:gap-16 items-center">
        <!-- Text -->
        <Motion
          is="div"
          :initial="{ opacity: 0, y: 40 }"
          :animate="{ opacity: 1, y: 0, transition: { duration: 0.8, ease: 'easeOut' } }"
          class="text-center lg:text-left"
        >
          <div class="inline-flex items-center gap-2 bg-green-700/50 backdrop-blur-sm text-green-200 text-sm font-medium px-4 py-2 rounded-full mb-6 border border-green-600/30">
            <DevicePhoneMobileIcon class="w-4 h-4" />
            <span>App de gestão rural</span>
          </div>

          <h1 class="text-4xl sm:text-5xl lg:text-6xl font-extrabold text-white leading-tight tracking-tight">
            Sua fazenda
            <span class="text-green-400">sob controle.</span>
            <br />No bolso.
          </h1>

          <p class="mt-6 text-lg sm:text-xl text-green-100/80 max-w-lg mx-auto lg:mx-0 leading-relaxed">
            Gerencie produção, finanças e clima da sua propriedade rural em um app simples e offline. Sem planilhas, sem papel, sem complicação.
          </p>

          <div class="mt-10 flex flex-col sm:flex-row gap-4 justify-center lg:justify-start">
            <a
              href="#lead-form"
              class="inline-flex items-center justify-center px-8 py-4 bg-green-500 hover:bg-green-400 text-green-950 font-bold rounded-xl text-lg transition-all duration-200 shadow-lg shadow-green-500/25 hover:shadow-green-400/30 hover:-translate-y-0.5"
            >
              Quero testar o app
            </a>
            <a
              href="#features"
              class="inline-flex items-center justify-center px-8 py-4 border-2 border-green-500/40 hover:border-green-400/60 text-green-200 hover:text-white font-semibold rounded-xl text-lg transition-all duration-200"
            >
              Ver funcionalidades
            </a>
          </div>
        </Motion>

        <!-- Phone mockups -->
        <Motion
          is="div"
          :initial="{ opacity: 0, y: 60 }"
          :animate="{ opacity: 1, y: 0, transition: { duration: 0.9, delay: 0.3, ease: 'easeOut' } }"
          class="relative flex justify-center items-end gap-4 lg:gap-6"
        >
          <div class="hidden sm:block -mb-8 opacity-80 scale-90">
            <PhoneMockup src="/screenshots/9-chuvas-entrada.png" alt="Controle de chuvas" size="sm" />
          </div>
          <div class="z-10 relative">
            <PhoneMockup src="/screenshots/1-dashboard.png" alt="Painel de controle" size="lg" />
          </div>
          <div class="hidden sm:block -mb-8 opacity-80 scale-90">
            <PhoneMockup src="/screenshots/6-financas-entrada-resumo.png" alt="Resumo financeiro" size="sm" />
          </div>
        </Motion>
      </div>
    </div>

    <!-- Scroll hint -->
    <div class="absolute bottom-8 left-1/2 -translate-x-1/2 text-green-400/60 animate-bounce">
      <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 14l-7 7m0 0l-7-7m7 7V3" />
      </svg>
    </div>
  </section>
</template>
