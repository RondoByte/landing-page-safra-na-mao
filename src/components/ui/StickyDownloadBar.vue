<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const visible = ref(false)

const handleScroll = () => {
  visible.value = window.scrollY > window.innerHeight * 0.6
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll, { passive: true })
  handleScroll()
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<template>
  <Transition
    enter-active-class="transition-all duration-300"
    enter-from-class="translate-y-full opacity-0"
    enter-to-class="translate-y-0 opacity-100"
    leave-active-class="transition-all duration-200"
    leave-from-class="translate-y-0 opacity-100"
    leave-to-class="translate-y-full opacity-0"
  >
    <div
      v-if="visible"
      class="sm:hidden fixed bottom-0 inset-x-0 z-40 bg-green-950/95 backdrop-blur-lg border-t border-green-700/40 px-4 py-3 shadow-[0_-8px_24px_rgba(0,0,0,0.35)]"
    >
      <a
        href="https://play.google.com/store/apps/details?id=com.faccinengenharia.agrocontrol&pli=1"
        target="_blank"
        rel="noopener noreferrer"
        aria-label="Baixar na Google Play"
        class="flex items-center justify-center gap-3 w-full bg-green-500 hover:bg-green-400 active:bg-green-600 text-green-950 font-bold py-3.5 px-5 rounded-xl text-base transition-colors shadow-lg shadow-green-500/30"
      >
        <svg class="w-6 h-6 shrink-0" viewBox="0 0 512 512" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
          <path d="M325.3 234.3L104.6 13l280.8 161.2-60.1 60.1zM47 0C34 6.8 25.3 19.2 25.3 35.3v441.3c0 16.1 8.7 28.5 21.7 35.3l256.6-256L47 0zm425.2 225.6l-58.9-34.1-65.7 64.5 65.7 64.5 60.1-34.1c18-14.3 18-46.5-1.2-60.8zM104.6 499l280.8-161.2-60.1-60.1L104.6 499z" fill="currentColor"/>
        </svg>
        Baixar grátis na Google Play
      </a>
    </div>
  </Transition>
</template>
