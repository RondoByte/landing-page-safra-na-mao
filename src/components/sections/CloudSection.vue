<script setup>
import { Motion } from 'motion-v'
import Card from 'primevue/card'
import {
  CloudArrowUpIcon,
  ArrowPathRoundedSquareIcon,
  GlobeAltIcon,
  ShieldCheckIcon,
  StarIcon,
  DevicePhoneMobileIcon,
  ServerStackIcon,
  LockClosedIcon,
  DocumentDuplicateIcon,
  SignalIcon,
} from '@heroicons/vue/24/outline'

const benefits = [
  {
    icon: CloudArrowUpIcon,
    title: 'Backup automático',
    description: 'Seus dados são salvos automaticamente na nuvem. Sem precisar lembrar, sem risco de esquecer.',
    color: 'text-sky-400',
    bg: 'bg-sky-500/15',
    border: 'border-sky-500/20',
    glow: 'group-hover:shadow-sky-500/10',
  },
  {
    icon: ArrowPathRoundedSquareIcon,
    title: 'Sincronização entre dispositivos',
    description: 'Trocou de celular? Seus dados acompanham você. Tudo sincronizado em tempo real.',
    color: 'text-violet-400',
    bg: 'bg-violet-500/15',
    border: 'border-violet-500/20',
    glow: 'group-hover:shadow-violet-500/10',
  },
  {
    icon: GlobeAltIcon,
    title: 'Acesso em qualquer lugar',
    description: 'No campo, em casa ou na cidade. Suas informações estão sempre disponíveis onde você estiver.',
    color: 'text-emerald-400',
    bg: 'bg-emerald-500/15',
    border: 'border-emerald-500/20',
    glow: 'group-hover:shadow-emerald-500/10',
  },
  {
    icon: ShieldCheckIcon,
    title: 'Segurança dos dados',
    description: 'Criptografia e servidores seguros. Suas informações protegidas contra perda, roubo ou falhas.',
    color: 'text-amber-400',
    bg: 'bg-amber-500/15',
    border: 'border-amber-500/20',
    glow: 'group-hover:shadow-amber-500/10',
  },
]

const syncDots = [0, 0.25, 0.5, 0.75]
</script>

<template>
  <section class="py-24 bg-gradient-to-b from-slate-900 via-slate-900 to-sky-950 relative overflow-hidden">
    <!-- Background -->
    <div class="absolute inset-0 pointer-events-none overflow-hidden">
      <div class="absolute top-20 left-1/4 w-[400px] h-[400px] bg-sky-500/8 rounded-full blur-3xl" />
      <div class="absolute bottom-10 right-1/4 w-[350px] h-[350px] bg-violet-500/8 rounded-full blur-3xl" />
      <div class="absolute inset-0 opacity-[0.03]" style="background-image: radial-gradient(circle, white 1px, transparent 1px); background-size: 32px 32px;" />
    </div>

    <div class="relative z-10 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <!-- Header -->
      <Motion
        is="div"
        :initial="{ opacity: 0, y: 30 }"
        :whileInView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
        :inViewOptions="{ once: true, amount: 0.3 }"
        class="text-center max-w-3xl mx-auto mb-20"
      >
        <div class="inline-flex items-center gap-2 bg-sky-500/10 backdrop-blur-sm text-sky-400 text-sm font-semibold px-4 py-1.5 rounded-full mb-6 border border-sky-500/20">
          <StarIcon class="w-4 h-4" />
          <span>Premium</span>
        </div>
        <h2 class="text-3xl sm:text-4xl lg:text-5xl font-extrabold text-white leading-tight">
          Seus dados da safra
          <span class="text-transparent bg-clip-text bg-gradient-to-r from-sky-400 to-violet-400">sempre seguros</span>
        </h2>
        <p class="mt-6 text-lg text-slate-400 leading-relaxed max-w-2xl mx-auto">
          Com o plano premium, todas as informações da produção são armazenadas na nuvem e protegidas contra perda de dados.
        </p>
      </Motion>

      <!-- ============================================ -->
      <!--  Sync Diagram: Phone → Cloud → Secure Store  -->
      <!-- ============================================ -->
      <Motion
        is="div"
        :initial="{ opacity: 0, y: 40 }"
        :whileInView="{ opacity: 1, y: 0, transition: { duration: 0.7, delay: 0.15, ease: 'easeOut' } }"
        :inViewOptions="{ once: true, amount: 0.2 }"
        class="mb-24"
      >
        <div class="flex flex-col lg:flex-row items-center justify-center gap-6 lg:gap-0">

          <!-- === NODE 1: Phone === -->
          <Motion
            is="div"
            :initial="{ opacity: 0, x: -30 }"
            :whileInView="{ opacity: 1, x: 0, transition: { duration: 0.5, delay: 0.1, ease: 'easeOut' } }"
            :inViewOptions="{ once: true }"
            class="relative"
          >
            <div class="absolute -inset-4 bg-sky-500/10 rounded-3xl blur-xl" />
            <div class="relative w-44 h-56 sm:w-48 sm:h-60 bg-slate-800/80 border border-slate-700/60 rounded-3xl flex flex-col items-center justify-center backdrop-blur-sm">
              <!-- Phone frame accents -->
              <div class="absolute top-3 left-1/2 -translate-x-1/2 w-12 h-1.5 bg-slate-700 rounded-full" />
              <DevicePhoneMobileIcon class="w-12 h-12 text-sky-400 mb-3" />
              <span class="text-sm font-bold text-white">Seu celular</span>
              <span class="text-xs text-slate-500 mt-1">Safra na Mão</span>
              <!-- Mini data rows -->
              <div class="mt-4 space-y-1.5 w-full px-5">
                <div class="flex items-center gap-2">
                  <div class="w-1.5 h-1.5 rounded-full bg-green-400" />
                  <div class="h-1.5 bg-slate-700 rounded-full flex-1" />
                </div>
                <div class="flex items-center gap-2">
                  <div class="w-1.5 h-1.5 rounded-full bg-green-400" />
                  <div class="h-1.5 bg-slate-700 rounded-full flex-1 max-w-[70%]" />
                </div>
                <div class="flex items-center gap-2">
                  <div class="w-1.5 h-1.5 rounded-full bg-green-400" />
                  <div class="h-1.5 bg-slate-700 rounded-full flex-1 max-w-[85%]" />
                </div>
              </div>
            </div>
          </Motion>

          <!-- === CONNECTOR 1: Phone → Cloud === -->
          <div class="flex lg:flex-row flex-col items-center lg:w-28 py-3 lg:py-0">
            <div class="flex lg:flex-row flex-col items-center gap-1.5">
              <Motion
                v-for="(d, i) in syncDots"
                :key="'a' + i"
                is="div"
                :animate="{ opacity: [0.2, 1, 0.2], scale: [0.6, 1.1, 0.6], transition: { duration: 1.8, delay: d, repeat: Infinity, ease: 'easeInOut' } }"
                class="w-2 h-2 rounded-full bg-sky-400"
              />
            </div>
          </div>

          <!-- === NODE 2: Cloud === -->
          <Motion
            is="div"
            :initial="{ opacity: 0, scale: 0.8 }"
            :whileInView="{ opacity: 1, scale: 1, transition: { duration: 0.6, delay: 0.3, ease: 'easeOut' } }"
            :inViewOptions="{ once: true }"
            class="relative"
          >
            <!-- Pulsing ring -->
            <Motion
              is="div"
              :animate="{ scale: [1, 1.15, 1], opacity: [0.15, 0.05, 0.15], transition: { duration: 3, repeat: Infinity, ease: 'easeInOut' } }"
              class="absolute -inset-6 bg-sky-400 rounded-full"
            />
            <div class="absolute -inset-4 bg-sky-500/10 rounded-full blur-xl" />
            <div class="relative w-36 h-36 sm:w-44 sm:h-44 bg-gradient-to-br from-sky-500/20 to-violet-500/20 rounded-full border border-sky-500/25 flex flex-col items-center justify-center backdrop-blur-sm">
              <CloudArrowUpIcon class="w-14 h-14 sm:w-16 sm:h-16 text-sky-400" />
              <span class="text-xs font-bold text-sky-300 mt-2 tracking-wide">CLOUD SYNC</span>
            </div>
          </Motion>

          <!-- === CONNECTOR 2: Cloud → Storage === -->
          <div class="flex lg:flex-row flex-col items-center lg:w-28 py-3 lg:py-0">
            <div class="flex lg:flex-row flex-col items-center gap-1.5">
              <Motion
                v-for="(d, i) in syncDots"
                :key="'b' + i"
                is="div"
                :animate="{ opacity: [0.2, 1, 0.2], scale: [0.6, 1.1, 0.6], transition: { duration: 1.8, delay: d + 1, repeat: Infinity, ease: 'easeInOut' } }"
                class="w-2 h-2 rounded-full bg-violet-400"
              />
            </div>
          </div>

          <!-- === NODE 3: Secure Storage === -->
          <Motion
            is="div"
            :initial="{ opacity: 0, x: 30 }"
            :whileInView="{ opacity: 1, x: 0, transition: { duration: 0.5, delay: 0.5, ease: 'easeOut' } }"
            :inViewOptions="{ once: true }"
            class="relative"
          >
            <div class="absolute -inset-4 bg-violet-500/10 rounded-3xl blur-xl" />
            <div class="relative w-44 h-56 sm:w-48 sm:h-60 bg-slate-800/80 border border-slate-700/60 rounded-3xl flex flex-col items-center justify-center backdrop-blur-sm">
              <div class="relative mb-3">
                <ServerStackIcon class="w-12 h-12 text-violet-400" />
                <div class="absolute -top-1 -right-1 w-5 h-5 bg-emerald-500/20 border border-emerald-500/40 rounded-full flex items-center justify-center">
                  <LockClosedIcon class="w-3 h-3 text-emerald-400" />
                </div>
              </div>
              <span class="text-sm font-bold text-white">Armazenamento</span>
              <span class="text-xs text-slate-500 mt-1">Seguro e criptografado</span>
              <!-- Mini status indicators -->
              <div class="mt-4 space-y-2 w-full px-5">
                <div class="flex items-center justify-between">
                  <div class="flex items-center gap-1.5">
                    <DocumentDuplicateIcon class="w-3 h-3 text-slate-500" />
                    <span class="text-[10px] text-slate-500">Backup</span>
                  </div>
                  <div class="flex items-center gap-1">
                    <div class="w-1.5 h-1.5 rounded-full bg-emerald-400" />
                    <span class="text-[10px] text-emerald-400 font-medium">OK</span>
                  </div>
                </div>
                <div class="flex items-center justify-between">
                  <div class="flex items-center gap-1.5">
                    <SignalIcon class="w-3 h-3 text-slate-500" />
                    <span class="text-[10px] text-slate-500">Sync</span>
                  </div>
                  <div class="flex items-center gap-1">
                    <div class="w-1.5 h-1.5 rounded-full bg-emerald-400" />
                    <span class="text-[10px] text-emerald-400 font-medium">OK</span>
                  </div>
                </div>
                <div class="flex items-center justify-between">
                  <div class="flex items-center gap-1.5">
                    <ShieldCheckIcon class="w-3 h-3 text-slate-500" />
                    <span class="text-[10px] text-slate-500">Seguro</span>
                  </div>
                  <div class="flex items-center gap-1">
                    <div class="w-1.5 h-1.5 rounded-full bg-emerald-400" />
                    <span class="text-[10px] text-emerald-400 font-medium">OK</span>
                  </div>
                </div>
              </div>
            </div>
          </Motion>
        </div>

        <!-- Caption -->
        <p class="text-center text-sm text-slate-500 mt-10">
          <span class="text-sky-400/80">Celular</span>
          &nbsp;&rarr;&nbsp;
          <span class="text-sky-400/80">Nuvem</span>
          &nbsp;&rarr;&nbsp;
          <span class="text-violet-400/80">Armazenamento seguro</span>
          &nbsp;&mdash;&nbsp;Sempre sincronizado.
        </p>
      </Motion>

      <!-- ============================================ -->
      <!--  Benefit Cards (PrimeVue)                    -->
      <!-- ============================================ -->
      <div class="grid sm:grid-cols-2 lg:grid-cols-4 gap-6">
        <Motion
          v-for="(benefit, i) in benefits"
          :key="i"
          is="div"
          :initial="{ opacity: 0, y: 30 }"
          :whileInView="{ opacity: 1, y: 0, transition: { duration: 0.5, delay: i * 0.1, ease: 'easeOut' } }"
          :inViewOptions="{ once: true, amount: 0.2 }"
          class="group"
        >
          <Card :class="['!bg-white/[0.04] !border !rounded-2xl hover:!bg-white/[0.08] transition-all duration-300 h-full shadow-lg shadow-transparent', benefit.border, benefit.glow]">
            <template #content>
              <div class="p-2">
                <div :class="['w-12 h-12 rounded-xl flex items-center justify-center mb-5', benefit.bg]">
                  <component :is="benefit.icon" :class="['w-6 h-6', benefit.color]" />
                </div>
                <h3 class="text-lg font-bold text-white mb-2">{{ benefit.title }}</h3>
                <p class="text-sm text-slate-400 leading-relaxed">{{ benefit.description }}</p>
              </div>
            </template>
          </Card>
        </Motion>
      </div>

      <!-- CTA -->
      <Motion
        is="div"
        :initial="{ opacity: 0, y: 20 }"
        :whileInView="{ opacity: 1, y: 0, transition: { duration: 0.5, delay: 0.4, ease: 'easeOut' } }"
        :inViewOptions="{ once: true }"
        class="text-center mt-16"
      >
        <a
          href="Safranamao.com.br"
          target="_blank"
          rel="noopener noreferrer"
          class="inline-flex items-center gap-2 px-8 py-4 bg-gradient-to-r from-sky-500 to-violet-500 hover:from-sky-400 hover:to-violet-400 text-white font-bold rounded-xl text-lg transition-all duration-200 shadow-lg shadow-sky-500/20 hover:-translate-y-0.5"
        >
          <CloudArrowUpIcon class="w-5 h-5" />
          Acessar o sistema
        </a>
      </Motion>
    </div>
  </section>
</template>
