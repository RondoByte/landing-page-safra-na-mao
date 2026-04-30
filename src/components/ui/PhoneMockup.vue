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
    <div class="relative rounded-[2.8rem] border-[6px] border-gray-900 bg-gray-900 shadow-2xl overflow-hidden">
      <!-- iPhone notch -->
      <div class="absolute top-0 inset-x-0 z-10 flex justify-center">
        <div class="w-24 h-6 bg-gray-900 rounded-b-2xl" />
      </div>

      <!-- Screen -->
      <div class="relative overflow-hidden bg-black aspect-[428/926]">
        <img
          :src="src"
          :alt="alt"
          class="w-full h-full object-cover"
          loading="lazy"
        />
      </div>
    </div>
  </div>
</template>
