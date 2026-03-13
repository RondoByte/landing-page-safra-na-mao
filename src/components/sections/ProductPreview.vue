<script setup>
import { Motion } from 'motion-v'
import { ref, onMounted, onUnmounted, computed } from 'vue'
import PhoneMockup from '../ui/PhoneMockup.vue'
import { ChevronLeftIcon, ChevronRightIcon } from '@heroicons/vue/24/solid'

const screens = [
  { src: '/screenshots/1-dashboard.png', label: 'Painel de controle' },
  { src: '/screenshots/4-producao-setor-infos.png', label: 'Detalhes por setor' },
  { src: '/screenshots/6-financas-entrada-resumo.png', label: 'Visão financeira' },
  { src: '/screenshots/7-financas-registro-depsesa.png', label: 'Registro de despesas' },
  { src: '/screenshots/8-financas-financiamento.png', label: 'Financiamentos' },
  { src: '/screenshots/10-pragas-entrada.png', label: 'Controle de pragas' },
  { src: '/screenshots/11-pragas-nova-aplicacao.png', label: 'Aplicação de defensivos' },
  { src: '/screenshots/9-chuvas-entrada.png', label: 'Controle de chuvas' },
  { src: '/screenshots/13-opcoes.png', label: 'Exportar dados' },
]

const track = ref(null)
const isDragging = ref(false)
const startX = ref(0)
const scrollStart = ref(0)
const hasDragged = ref(false)
const activeIndex = ref(0)

function onPointerDown(e) {
  if (!track.value) return
  track.value.setPointerCapture(e.pointerId)
  isDragging.value = true
  hasDragged.value = false
  startX.value = e.clientX
  scrollStart.value = track.value.scrollLeft
  track.value.style.cursor = 'grabbing'
  track.value.style.scrollSnapType = 'none'
}

function onPointerMove(e) {
  if (!isDragging.value || !track.value) return
  e.preventDefault()
  const dx = e.clientX - startX.value
  if (Math.abs(dx) > 3) hasDragged.value = true
  track.value.scrollLeft = scrollStart.value - dx
}

function onPointerUp(e) {
  if (!track.value) return
  if (track.value.hasPointerCapture(e.pointerId)) {
    track.value.releasePointerCapture(e.pointerId)
  }
  isDragging.value = false
  track.value.style.cursor = 'grab'
  track.value.style.scrollSnapType = 'x mandatory'
}

function updateActiveIndex() {
  if (!track.value) return
  const el = track.value
  const children = el.querySelectorAll('[data-slide]')
  if (!children.length) return

  if (el.scrollLeft <= 10) {
    activeIndex.value = 0
    return
  }
  if (el.scrollLeft + el.clientWidth >= el.scrollWidth - 10) {
    activeIndex.value = children.length - 1
    return
  }

  const center = el.scrollLeft + el.clientWidth / 2
  let closest = 0
  let minDist = Infinity
  children.forEach((child, i) => {
    const childCenter = child.offsetLeft + child.offsetWidth / 2
    const dist = Math.abs(center - childCenter)
    if (dist < minDist) {
      minDist = dist
      closest = i
    }
  })
  activeIndex.value = closest
}

function scrollTo(index) {
  if (!track.value) return
  const children = track.value.querySelectorAll('[data-slide]')
  if (!children[index]) return

  if (index === 0) {
    track.value.scrollTo({ left: 0, behavior: 'smooth' })
    return
  }
  if (index === children.length - 1) {
    track.value.scrollTo({ left: track.value.scrollWidth, behavior: 'smooth' })
    return
  }

  const child = children[index]
  const childCenter = child.offsetLeft + child.offsetWidth / 2
  const targetScroll = childCenter - track.value.clientWidth / 2
  track.value.scrollTo({ left: targetScroll, behavior: 'smooth' })
}

function prev() {
  scrollTo(Math.max(0, activeIndex.value - 1))
}

function next() {
  scrollTo(Math.min(screens.length - 1, activeIndex.value + 1))
}

const canPrev = computed(() => activeIndex.value > 0)
const canNext = computed(() => activeIndex.value < screens.length - 1)

onMounted(() => {
  if (track.value) {
    track.value.addEventListener('scroll', updateActiveIndex, { passive: true })
  }
})

onUnmounted(() => {
  if (track.value) {
    track.value.removeEventListener('scroll', updateActiveIndex)
  }
})
</script>

<template>
  <section class="py-24 bg-white overflow-hidden">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <Motion
        is="div"
        :initial="{ opacity: 0, y: 30 }"
        :whileInView="{ opacity: 1, y: 0, transition: { duration: 0.6, ease: 'easeOut' } }"
        :inViewOptions="{ once: true, amount: 0.3 }"
        class="text-center max-w-3xl mx-auto mb-16"
      >
        <span class="inline-block text-sm font-semibold text-green-700 bg-green-50 px-4 py-1.5 rounded-full mb-4 tracking-wide uppercase">Preview</span>
        <h2 class="text-3xl sm:text-4xl lg:text-5xl font-extrabold text-gray-900 leading-tight">
          Veja o app <span class="text-green-600">por dentro</span>
        </h2>
        <p class="mt-4 text-lg text-gray-500">
          Cada tela foi pensada para facilitar o dia a dia do produtor rural.
        </p>
      </Motion>
    </div>

    <Motion
      is="div"
      :initial="{ opacity: 0, y: 40 }"
      :whileInView="{ opacity: 1, y: 0, transition: { duration: 0.7, delay: 0.2, ease: 'easeOut' } }"
      :inViewOptions="{ once: true, amount: 0.1 }"
      class="relative"
    >
      <!-- Carousel track -->
      <div
        ref="track"
        class="flex gap-8 overflow-x-auto pb-8 snap-x snap-mandatory select-none carousel-track"
        style="cursor: grab; -webkit-overflow-scrolling: touch;"
        @pointerdown="onPointerDown"
        @pointermove="onPointerMove"
        @pointerup="onPointerUp"
        @pointercancel="onPointerUp"
        @dragstart.prevent
      >
        <!-- Dynamic spacers so first/last slides can be centered -->
        <div class="flex-shrink-0 carousel-spacer" />
        <div
          v-for="(screen, i) in screens"
          :key="i"
          data-slide
          class="flex-shrink-0 snap-center transition-opacity duration-300"
          :class="activeIndex === i ? 'opacity-100' : 'opacity-60'"
        >
          <PhoneMockup :src="screen.src" :alt="screen.label" size="md" />
          <p class="text-center text-sm font-medium text-gray-500 mt-4">{{ screen.label }}</p>
        </div>
        <div class="flex-shrink-0 carousel-spacer" />
      </div>

      <!-- Fade edges -->
      <div class="absolute inset-y-0 left-0 w-16 bg-gradient-to-r from-white to-transparent pointer-events-none" />
      <div class="absolute inset-y-0 right-0 w-16 bg-gradient-to-l from-white to-transparent pointer-events-none" />

      <!-- Arrow buttons -->
      <button
        v-show="canPrev"
        @click="prev"
        class="absolute left-4 lg:left-8 top-1/2 -translate-y-1/2 w-12 h-12 bg-white/90 backdrop-blur-sm border border-gray-200 rounded-full shadow-lg flex items-center justify-center hover:bg-green-50 hover:border-green-300 transition-all duration-200 z-10"
        aria-label="Anterior"
      >
        <ChevronLeftIcon class="w-5 h-5 text-gray-700" />
      </button>
      <button
        v-show="canNext"
        @click="next"
        class="absolute right-4 lg:right-8 top-1/2 -translate-y-1/2 w-12 h-12 bg-white/90 backdrop-blur-sm border border-gray-200 rounded-full shadow-lg flex items-center justify-center hover:bg-green-50 hover:border-green-300 transition-all duration-200 z-10"
        aria-label="Próximo"
      >
        <ChevronRightIcon class="w-5 h-5 text-gray-700" />
      </button>
    </Motion>

    <!-- Dot indicators -->
    <div class="flex items-center justify-center gap-2 mt-6">
      <button
        v-for="(screen, i) in screens"
        :key="i"
        @click="scrollTo(i)"
        class="rounded-full transition-all duration-300"
        :class="activeIndex === i
          ? 'w-8 h-3 bg-green-600'
          : 'w-3 h-3 bg-gray-300 hover:bg-gray-400'"
        :aria-label="`Ir para ${screen.label}`"
      />
    </div>
  </section>
</template>

<style scoped>
.carousel-track::-webkit-scrollbar {
  display: none;
}
.carousel-track {
  -ms-overflow-style: none;
  scrollbar-width: none;
}
.carousel-track img {
  -webkit-user-drag: none;
  user-select: none;
  pointer-events: none;
}
.carousel-spacer {
  width: calc(50vw - 130px - 1rem);
  min-width: 1rem;
}
</style>
