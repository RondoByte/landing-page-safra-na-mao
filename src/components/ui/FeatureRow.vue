<script setup>
import { Motion } from 'motion-v'
import PhoneMockup from './PhoneMockup.vue'

defineProps({
  feature: { type: Object, required: true },
  reversed: { type: Boolean, default: false },
})
</script>

<template>
  <Motion
    is="div"
    :initial="{ opacity: 0, y: 50 }"
    :whileInView="{ opacity: 1, y: 0, transition: { duration: 0.7, ease: 'easeOut' } }"
    :inViewOptions="{ once: true, amount: 0.2 }"
    class="grid lg:grid-cols-2 gap-12 lg:gap-20 items-center"
  >
    <div :class="['flex justify-center', reversed ? 'lg:order-2' : '']">
      <div class="relative">
        <div class="absolute -inset-6 bg-green-100/40 rounded-[3rem] blur-xl" />
        <div class="relative">
          <PhoneMockup :src="feature.screenshot" :alt="feature.alt" size="md" />
        </div>
      </div>
    </div>
    <div :class="[reversed ? 'lg:order-1' : '']">
      <span :class="['inline-block text-sm font-semibold px-4 py-1.5 rounded-full mb-4', feature.accent]">
        {{ feature.tag }}
      </span>
      <h3 class="text-2xl sm:text-3xl font-bold text-gray-900 leading-tight mb-4">
        {{ feature.title }}
      </h3>
      <p class="text-lg text-gray-500 leading-relaxed">
        {{ feature.description }}
      </p>
    </div>
  </Motion>
</template>
