<script setup>
import { Motion } from 'motion-v'
import {
  DocumentTextIcon,
  TableCellsIcon,
  CurrencyDollarIcon,
} from '@heroicons/vue/24/outline'

const problems = [
  {
    icon: DocumentTextIcon,
    title: 'Cadernos e papéis que se perdem',
    description: 'Anotações em papel desaparecem. Dados da safra anterior? Boa sorte procurando.',
    color: 'text-red-500',
    bg: 'bg-red-50',
    border: 'border-red-100',
  },
  {
    icon: TableCellsIcon,
    title: 'Planilhas confusas e desatualizadas',
    description: 'Aquela planilha do Excel que ninguém atualiza e ninguém confia nos números.',
    color: 'text-amber-500',
    bg: 'bg-amber-50',
    border: 'border-amber-100',
  },
  {
    icon: CurrencyDollarIcon,
    title: 'Sem visão financeira real',
    description: 'Quanto gastou com insumos? Qual foi o lucro da safra? Ninguém sabe responder na hora.',
    color: 'text-orange-500',
    bg: 'bg-orange-50',
    border: 'border-orange-100',
  },
]
</script>

<template>
  <section class="py-24 bg-gray-50">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <Motion
        is="div"
        :initial="{ opacity: 0, y: 40 }"
        :whileInView="{ opacity: 1, y: 0, transition: { duration: 0.7, ease: 'easeOut' } }"
        :inViewOptions="{ once: true, amount: 0.3 }"
        class="text-center max-w-3xl mx-auto mb-16"
      >
        <span class="inline-block text-sm font-semibold text-red-500 bg-red-50 px-4 py-1.5 rounded-full mb-4 tracking-wide uppercase">O problema</span>
        <h2 class="text-3xl sm:text-4xl lg:text-5xl font-extrabold text-gray-900 leading-tight">
          O produtor rural gerencia milhões...
          <span class="text-red-500">em cadernos e planilhas.</span>
        </h2>
        <p class="mt-6 text-lg text-gray-500 leading-relaxed">
          Ferramentas ultrapassadas geram perda de dados, decisões erradas e prejuízo financeiro. O campo precisa de tecnologia acessível.
        </p>
      </Motion>

      <div class="grid md:grid-cols-3 gap-8">
        <Motion
          v-for="(problem, i) in problems"
          :key="i"
          is="div"
          :initial="{ opacity: 0, y: 40 }"
          :whileInView="{ opacity: 1, y: 0, transition: { duration: 0.5, delay: i * 0.15, ease: 'easeOut' } }"
          :inViewOptions="{ once: true, amount: 0.2 }"
          :class="['group rounded-2xl p-8 border-2 transition-all duration-300 hover:-translate-y-1 hover:shadow-lg', problem.bg, problem.border]"
        >
          <div :class="['w-14 h-14 rounded-xl flex items-center justify-center mb-6', problem.bg]">
            <component :is="problem.icon" :class="['w-7 h-7', problem.color]" />
          </div>
          <h3 class="text-xl font-bold text-gray-900 mb-3">{{ problem.title }}</h3>
          <p class="text-gray-600 leading-relaxed">{{ problem.description }}</p>
        </Motion>
      </div>
    </div>
  </section>
</template>
