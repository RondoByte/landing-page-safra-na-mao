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
      <div class="flex items-center gap-2 w-full">
        <a
          href="https://play.google.com/store/apps/details?id=com.faccinengenharia.agrocontrol&pli=1"
          target="_blank"
          rel="noopener noreferrer"
          aria-label="Baixar na Google Play"
          class="flex items-center justify-center gap-2 flex-1 bg-green-500 hover:bg-green-400 active:bg-green-600 text-green-950 font-bold py-3.5 px-3 rounded-xl text-sm transition-colors shadow-lg shadow-green-500/30"
        >
          <svg class="w-5 h-5 shrink-0" viewBox="0 0 512 512" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
            <path d="M325.3 234.3L104.6 13l280.8 161.2-60.1 60.1zM47 0C34 6.8 25.3 19.2 25.3 35.3v441.3c0 16.1 8.7 28.5 21.7 35.3l256.6-256L47 0zm425.2 225.6l-58.9-34.1-65.7 64.5 65.7 64.5 60.1-34.1c18-14.3 18-46.5-1.2-60.8zM104.6 499l280.8-161.2-60.1-60.1L104.6 499z" fill="currentColor"/>
          </svg>
          Google Play
        </a>
        <a
          href="https://apps.apple.com/br/app/safra-na-m%C3%A3o-controle-rural/id6764441084"
          target="_blank"
          rel="noopener noreferrer"
          aria-label="Baixar na App Store"
          class="flex items-center justify-center gap-2 flex-1 bg-white hover:bg-gray-100 active:bg-gray-200 text-gray-900 font-bold py-3.5 px-3 rounded-xl text-sm transition-colors shadow-lg"
        >
          <svg class="w-5 h-5 shrink-0" viewBox="0 0 814 1000" xmlns="http://www.w3.org/2000/svg" aria-hidden="true" fill="currentColor">
            <path d="M788.1 340.9c-5.8 4.5-108.2 62.2-108.2 190.5 0 148.4 130.3 200.9 134.2 202.2-.6 3.2-20.7 71.9-68.7 141.9-42.8 61.6-87.5 123.1-155.5 123.1s-85.5-39.5-164-39.5c-76 0-103.7 40.8-165.9 40.8s-105-57.8-155.5-127.4C46 383.8 156.7 326.5 116.7 255.1C106 241.4 96.3 232.6 80.1 232.6 65.6 232.6 12.7 283.8 0 341.5 0 395.7 29.8 441.2 87 441.2c48.9 0 91.8-32.9 108.2-67.1 0 0 27.7 115.9 29.9 116.6 11.7 38.4 31.4 61.1 77.5 61.1 42.3 0 73-19.1 89.9-67.1 32.8-93.4 36.5-179.4 36.5-232.2 0-141.4-114.3-190.5-185.2-190.5-68.1 0-113.1 38.6-132.6 38.6-19.3 0-61.5-38.6-129.6-38.6C38.9.3 0 43.5 0 43.5v163.9c0 16.1 13.1 29.2 29.3 29.2h17.9l-.1 6c0 90.6 73.3 164.4 163.4 164.4 29.7 0 57.7-7.9 82.5-22.2V741c0 143.5-116.6 260.1-260.3 260.1h-14.4c-16.2 0-29.3 13.1-29.3 29.2v25.8c0 16.1 13.1 29.2 29.3 29.2H814v-25.8c0-16.1-13.1-29.2-29.3-29.2h-14.4C627 1001.1 510.4 884.5 510.4 741V384.4c24.8 14.3 52.7 22.2 82.5 22.2 90.1 0 163.4-73.8 163.4-164.4l-.1-6h17.9c16.2 0 29.3-13.1 29.3-29.2V43.5S776.4.3 738.1.3c-68.1 0-110.3 38.3-129.6 38.3-19.5 0-64.4-38.3-132.6-38.3-70.9 0-185.2 49.1-185.2 190.5 0 52.8 3.7 138.8 36.5 232.2 16.9 48 47.6 67.1 89.9 67.1 46.1 0 65.8-22.7 77.5-61.1 2.2-.7 29.9-116.6 29.9-116.6 16.4 34.2 59.3 67.1 108.2 67.1 57.2 0 87-45.5 87-99.7-16.2-57.7-69.1-108.9-83.6-108.9z"/>
          </svg>
          App Store
        </a>
      </div>
    </div>
  </Transition>
</template>
