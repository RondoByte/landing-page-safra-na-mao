<script setup>
import { Motion } from 'motion-v'
import PhoneMockup from '../ui/PhoneMockup.vue'
import { DevicePhoneMobileIcon } from '@heroicons/vue/24/outline'
</script>

<template>
  <section class="relative min-h-screen flex items-center overflow-hidden bg-gradient-to-br from-green-900 via-green-800 to-green-950 pt-14">
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

          <div class="mt-10">
            <a
              href="https://play.google.com/store/apps/details?id=com.faccinengenharia.agrocontrol&pli=1"
              target="_blank"
              rel="noopener noreferrer"
              aria-label="Baixar Safra na Mão na Google Play"
              class="group inline-block rounded-xl transition-all duration-200 hover:-translate-y-0.5 hover:drop-shadow-[0_8px_24px_rgba(74,222,128,0.35)] focus:outline-none focus:ring-4 focus:ring-green-400/40"
            >
              <img
                src="/pt-BR.svg"
                alt="Disponível no Google Play"
                class="h-20 sm:h-24 lg:h-28 w-auto"
              />
            </a>

            <ul class="mt-4 flex flex-wrap items-center justify-center lg:justify-start gap-x-5 gap-y-2 text-sm text-green-200/90">
              <li class="inline-flex items-center gap-1.5">
                <svg class="w-4 h-4 text-green-400" viewBox="0 0 20 20" fill="currentColor"><path fill-rule="evenodd" d="M16.7 5.3a1 1 0 010 1.4l-8 8a1 1 0 01-1.4 0l-4-4a1 1 0 111.4-1.4L8 12.6l7.3-7.3a1 1 0 011.4 0z" clip-rule="evenodd"/></svg>
                Grátis para baixar
              </li>
              <li class="inline-flex items-center gap-1.5">
                <svg class="w-4 h-4 text-green-400" viewBox="0 0 20 20" fill="currentColor"><path fill-rule="evenodd" d="M16.7 5.3a1 1 0 010 1.4l-8 8a1 1 0 01-1.4 0l-4-4a1 1 0 111.4-1.4L8 12.6l7.3-7.3a1 1 0 011.4 0z" clip-rule="evenodd"/></svg>
                Funciona offline
              </li>
              <li class="inline-flex items-center gap-1.5">
                <svg class="w-4 h-4 text-green-400" viewBox="0 0 20 20" fill="currentColor"><path fill-rule="evenodd" d="M16.7 5.3a1 1 0 010 1.4l-8 8a1 1 0 01-1.4 0l-4-4a1 1 0 111.4-1.4L8 12.6l7.3-7.3a1 1 0 011.4 0z" clip-rule="evenodd"/></svg>
                Sem mensalidade obrigatória
              </li>
            </ul>

            <div class="mt-6 flex flex-wrap items-center justify-center lg:justify-start gap-x-6 gap-y-2 text-sm">
              <a
                href="/webapp/"
                target="_blank"
                rel="noopener noreferrer"
                class="text-green-200 hover:text-white underline underline-offset-4 decoration-green-400/50 hover:decoration-green-300 transition-colors inline-flex items-center gap-1.5"
              >
                Prefere no navegador? Testar versão web
                <svg class="w-3.5 h-3.5" viewBox="0 0 20 20" fill="currentColor"><path fill-rule="evenodd" d="M5.22 14.78a.75.75 0 001.06 0l7.22-7.22v5.69a.75.75 0 001.5 0v-7.5a.75.75 0 00-.75-.75h-7.5a.75.75 0 000 1.5h5.69l-7.22 7.22a.75.75 0 000 1.06z" clip-rule="evenodd"/></svg>
              </a>
              <a
                href="#features"
                class="text-green-300/80 hover:text-white transition-colors"
              >
                Ver funcionalidades ↓
              </a>
            </div>
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
