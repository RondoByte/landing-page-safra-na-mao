<script setup>
import { Motion } from 'motion-v'
import FeatureRow from '../ui/FeatureRow.vue'

const features = [
  {
    tag: 'Produção',
    title: 'Cadeias produtivas organizadas por setor',
    description: 'Cadastre suas culturas, divida por setores e acompanhe a produção em sacas, quilos ou a unidade que preferir. Registre colheitas, vendas e insumos com data e valor.',
    screenshot: '/screenshots/4-producao-setor-infos.png',
    alt: 'Detalhes do setor de produção',
    accent: 'bg-green-50 text-green-700',
  },
  {
    tag: 'Finanças',
    title: 'Visão financeira completa da propriedade',
    description: 'Acompanhe saldo geral, receitas e despesas por setor, despesas globais e um gráfico de 6 meses. Tudo para saber exatamente como está a saúde financeira da safra.',
    screenshot: '/screenshots/6-financas-entrada-resumo.png',
    alt: 'Resumo financeiro com gráfico',
    accent: 'bg-emerald-50 text-emerald-700',
  },
  {
    tag: 'Pragas',
    title: 'Monitoramento e controle de pragas',
    description: 'Registre ocorrências, acompanhe o nível de ataque e documente aplicações de defensivos com produto, dose e responsável. Tudo rastreável.',
    screenshot: '/screenshots/10-pragas-entrada.png',
    alt: 'Controle de pragas',
    accent: 'bg-orange-50 text-orange-700',
  },
  {
    tag: 'Clima',
    title: 'Registro de chuvas dia a dia',
    description: 'Acompanhe a precipitação diária e mensal na sua região. Histórico completo para tomar melhores decisões de plantio e manejo.',
    screenshot: '/screenshots/9-chuvas-entrada.png',
    alt: 'Controle de chuvas',
    accent: 'bg-blue-50 text-blue-700',
  },
  {
    tag: 'Financiamentos',
    title: 'Cálculo automático de juros',
    description: 'Controle empréstimos e financiamentos rurais com cálculo de juros simples ou compostos. Saiba exatamente quanto falta pagar.',
    screenshot: '/screenshots/8-financas-financiamento.png',
    alt: 'Controle de financiamentos',
    accent: 'bg-amber-50 text-amber-700',
  },
]
</script>

<template>
  <section id="features" class="py-24 bg-gray-50">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <Motion
        is="div"
        :initial="{ opacity: 0, y: 30 }"
        :whileInView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
        :inViewOptions="{ once: true, amount: 0.3 }"
        class="text-center max-w-3xl mx-auto mb-20"
      >
        <span class="inline-block text-sm font-semibold text-green-700 bg-green-50 px-4 py-1.5 rounded-full mb-4 tracking-wide uppercase">Funcionalidades</span>
        <h2 class="text-3xl sm:text-4xl lg:text-5xl font-extrabold text-gray-900 leading-tight">
          Tudo que sua propriedade precisa.
          <span class="text-green-600">Nada que ela não precisa.</span>
        </h2>
      </Motion>

      <div class="space-y-24">
        <FeatureRow
          v-for="(feature, i) in features"
          :key="i"
          :feature="feature"
          :reversed="i % 2 !== 0"
        />
      </div>
    </div>
  </section>
</template>
