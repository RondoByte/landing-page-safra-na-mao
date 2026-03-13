<script setup>
defineProps({
  src: { type: String, required: true },
  alt: { type: String, default: 'App screenshot' },
  size: { type: String, default: 'md', validator: (v) => ['sm', 'md', 'lg'].includes(v) },
})

const sizeClasses = {
  sm: 'w-[200px]',
  md: 'w-[260px]',
  lg: 'w-[300px]',
}
</script>

<template>
  <div :class="['relative mx-auto', sizeClasses[size]]">
    <div class="relative rounded-[2.5rem] border-[6px] border-gray-900 bg-gray-900 shadow-2xl overflow-hidden">
      <!-- Notch -->

      <!-- Screen -->
      <div class="relative overflow-hidden bg-white aspect-[9/16]">
        <img
          :src="src"
          :alt="alt"
          class="w-full h-full object-contain"
          loading="lazy"
        />
      </div>
    </div>
  </div>
</template>
