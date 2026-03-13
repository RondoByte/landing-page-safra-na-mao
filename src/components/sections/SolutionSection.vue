<script setup>
import { Motion } from 'motion-v'
import PhoneMockup from '../ui/PhoneMockup.vue'
import {
  DevicePhoneMobileIcon,
  ArrowPathIcon,
  ChartBarIcon,
} from '@heroicons/vue/24/outline'
import { CheckCircleIcon } from '@heroicons/vue/24/solid'

const bullets = [
  { icon: DevicePhoneMobileIcon, text: 'Registre tudo no celular, em segundos' },
  { icon: ArrowPathIcon, text: 'Dados organizados e sempre atualizados' },
  { icon: ChartBarIcon, text: 'Resumo financeiro instantâneo por safra' },
]
</script>

<template>
  <section class="py-24 bg-white">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="grid lg:grid-cols-2 gap-16 items-center">
        <!-- Text -->
        <Motion
          is="div"
          :initial="{ opacity: 0, x: -40 }"
          :whileInView="{ opacity: 1, x: 0, transition: { duration: 0.7, ease: 'easeOut' } }"
          :inViewOptions="{ once: true, amount: 0.3 }"
        >
          <span class="inline-block text-sm font-semibold text-green-700 bg-green-50 px-4 py-1.5 rounded-full mb-4 tracking-wide uppercase">A solução</span>
          <h2 class="text-3xl sm:text-4xl lg:text-5xl font-extrabold text-gray-900 leading-tight">
            Um app feito por quem
            <span class="text-green-600">entende o campo.</span>
          </h2>
          <p class="mt-6 text-lg text-gray-500 leading-relaxed">
            O Agro Controle reúne tudo que você precisa em um único lugar: produção, finanças, chuvas e muito mais. Funciona no celular, é simples de usar, e coloca o controle da sua propriedade na palma da mão.
          </p>

          <div class="mt-10 space-y-5">
            <div
              v-for="(bullet, i) in bullets"
              :key="i"
              class="flex items-start gap-4"
            >
              <div class="flex-shrink-0 w-10 h-10 bg-green-100 rounded-xl flex items-center justify-center">
                <component :is="bullet.icon" class="w-5 h-5 text-green-700" />
              </div>
              <div class="flex items-center gap-2 pt-2">
                <CheckCircleIcon class="w-5 h-5 text-green-500 flex-shrink-0" />
                <span class="text-gray-700 font-medium text-lg">{{ bullet.text }}</span>
              </div>
            </div>
          </div>

          <div class="mt-10">
            <a
              href="#lead-form"
              class="inline-flex items-center justify-center px-8 py-4 bg-green-600 hover:bg-green-700 text-white font-bold rounded-xl text-lg transition-all duration-200 shadow-lg shadow-green-600/20 hover:-translate-y-0.5"
            >
              Quero experimentar
            </a>
          </div>
        </Motion>

        <!-- Phone -->
        <Motion
          is="div"
          :initial="{ opacity: 0, x: 40 }"
          :whileInView="{ opacity: 1, x: 0, transition: { duration: 0.7, delay: 0.2, ease: 'easeOut' } }"
          :inViewOptions="{ once: true, amount: 0.3 }"
          class="flex justify-center"
        >
          <div class="relative">
            <div class="absolute -inset-8 bg-green-100/50 rounded-[3rem] blur-2xl" />
            <div class="relative">
              <PhoneMockup src="/screenshots/1-dashboard.png" alt="Painel de controle com resumo financeiro" size="lg" />
            </div>
          </div>
        </Motion>
      </div>
    </div>
  </section>
</template>
