<script setup>
import { DevicePhoneMobileIcon } from '@heroicons/vue/24/outline'
</script>

<template>
  <section class="relative py-20 overflow-hidden bg-gradient-to-br from-green-900 via-green-800 to-green-950">
    <div class="absolute inset-0 overflow-hidden pointer-events-none">
      <div class="absolute -top-20 -right-20 w-[400px] h-[400px] bg-green-500/10 rounded-full blur-3xl" />
      <div class="absolute -bottom-20 -left-20 w-[400px] h-[400px] bg-green-600/15 rounded-full blur-3xl" />
    </div>

    <div class="relative z-10 max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 text-center">
      <div class="inline-flex items-center gap-2 bg-green-700/50 backdrop-blur-sm text-green-200 text-sm font-medium px-4 py-2 rounded-full mb-6 border border-green-600/30">
        <DevicePhoneMobileIcon class="w-4 h-4" />
        <span>Pronto para começar?</span>
      </div>

      <h2 class="text-3xl sm:text-4xl lg:text-5xl font-extrabold text-white leading-tight tracking-tight">
        Leve sua gestão rural
        <span class="text-green-400">para o campo.</span>
      </h2>

      <p class="mt-5 text-lg text-green-100/80 max-w-xl mx-auto">
        Instale o Safra na Mão no seu celular e comece a registrar sua produção hoje mesmo. Sem cadastros demorados.
      </p>

      <div class="mt-10 flex flex-col items-center gap-4">
        <a
          href="https://play.google.com/store/apps/details?id=com.faccinengenharia.agrocontrol&pli=1"
          target="_blank"
          rel="noopener noreferrer"
          aria-label="Baixar Safra na Mão na Google Play"
          class="inline-block rounded-xl transition-all duration-200 hover:-translate-y-0.5 hover:drop-shadow-[0_8px_24px_rgba(74,222,128,0.35)] focus:outline-none focus:ring-4 focus:ring-green-400/40"
        >
          <img
            src="/pt-BR.svg"
            alt="Disponível no Google Play"
            class="h-20 sm:h-24 lg:h-28 w-auto"
          />
        </a>

        <p class="text-sm text-green-200/70">
          Grátis · Funciona offline · Feito para o produtor brasileiro
        </p>
      </div>
    </div>
  </section>
</template>
