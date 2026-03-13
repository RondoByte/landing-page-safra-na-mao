<script setup>
import { Motion } from 'motion-v'
import StepCard from '../ui/StepCard.vue'

const steps = [
  {
    number: '01',
    title: 'Cadastre sua produção',
    description: 'Crie suas cadeias produtivas (café, soja, gado...) e organize por setores da propriedade.',
    screenshot: '/screenshots/4-producao-setor-infos.png',
    alt: 'Cadastro de produção por setor',
  },
  {
    number: '02',
    title: 'Registre tudo no dia a dia',
    description: 'Adicione colheitas, vendas, despesas, aplicações de defensivos e chuvas. Tudo em poucos toques.',
    screenshot: '/screenshots/11-pragas-nova-aplicacao.png',
    alt: 'Registro de aplicação de defensivos',
  },
  {
    number: '03',
    title: 'Acompanhe seus resultados',
    description: 'Veja o painel com saldo, gráficos e alertas. Tome decisões com dados reais.',
    screenshot: '/screenshots/1-dashboard.png',
    alt: 'Dashboard com resultados',
  },
]
</script>

<template>
  <section class="py-24 bg-green-950 relative overflow-hidden">
    <div class="absolute inset-0 pointer-events-none">
      <div class="absolute top-0 right-0 w-[500px] h-[500px] bg-green-800/30 rounded-full blur-3xl" />
      <div class="absolute bottom-0 left-0 w-[400px] h-[400px] bg-green-700/20 rounded-full blur-3xl" />
    </div>

    <div class="relative z-10 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <Motion
        is="div"
        :initial="{ opacity: 0, y: 30 }"
        :whileInView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
        :inViewOptions="{ once: true, amount: 0.3 }"
        class="text-center max-w-3xl mx-auto mb-20"
      >
        <span class="inline-block text-sm font-semibold text-green-400 bg-green-900/50 px-4 py-1.5 rounded-full mb-4 tracking-wide uppercase border border-green-800">Como funciona</span>
        <h2 class="text-3xl sm:text-4xl lg:text-5xl font-extrabold text-white leading-tight">
          Comece em <span class="text-green-400">3 passos</span>
        </h2>
        <p class="mt-4 text-lg text-green-200/70">
          Do download ao controle total da sua propriedade em minutos.
        </p>
      </Motion>

      <div class="grid md:grid-cols-3 gap-12">
        <StepCard v-for="(step, i) in steps" :key="i" :step="step" :index="i" />
      </div>
    </div>
  </section>
</template>
