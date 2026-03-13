<script setup>
import { Motion } from 'motion-v'
import PhoneMockup from './PhoneMockup.vue'

defineProps({
  step: { type: Object, required: true },
  index: { type: Number, default: 0 },
})
</script>

<template>
  <Motion
    is="div"
    :initial="{ opacity: 0, y: 50 }"
    :whileInView="{ opacity: 1, y: 0, transition: { duration: 0.6, delay: index * 0.2, ease: 'easeOut' } }"
    :inViewOptions="{ once: true, amount: 0.2 }"
    class="text-center"
  >
    <div class="relative inline-block mb-8">
      <div class="absolute -inset-4 bg-green-800/30 rounded-[2rem] blur-lg" />
      <div class="relative">
        <PhoneMockup :src="step.screenshot" :alt="step.alt" size="sm" />
      </div>
    </div>
    <div class="inline-flex items-center justify-center w-10 h-10 rounded-full bg-green-500 text-green-950 font-bold text-sm mb-4">
      {{ step.number }}
    </div>
    <h3 class="text-xl font-bold text-white mb-3">{{ step.title }}</h3>
    <p class="text-green-200/70 leading-relaxed">{{ step.description }}</p>
  </Motion>
</template>
