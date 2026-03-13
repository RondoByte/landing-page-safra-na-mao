<script setup>
import { Motion } from 'motion-v'
import { ref, reactive } from 'vue'
import InputText from 'primevue/inputtext'
import Button from 'primevue/button'
import {
  UserIcon,
  EnvelopeIcon,
  PhoneIcon,
  ShieldCheckIcon,
  BoltIcon,
  HeartIcon,
} from '@heroicons/vue/24/outline'
import { CheckCircleIcon } from '@heroicons/vue/24/solid'

const form = reactive({
  name: '',
  email: '',
  phone: '',
})

const submitted = ref(false)
const loading = ref(false)

const handleSubmit = async () => {
  if (!form.name || !form.email || !form.phone) return
  loading.value = true
  await new Promise((r) => setTimeout(r, 1500))
  loading.value = false
  submitted.value = true
}

const trustItems = [
  { icon: BoltIcon, text: '100% gratuito durante o beta' },
  { icon: ShieldCheckIcon, text: 'Seus dados estão seguros' },
  { icon: HeartIcon, text: 'Sem spam, prometemos' },
]
</script>

<template>
  <section id="lead-form" class="py-24 bg-gray-50">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <Motion
        is="div"
        :initial="{ opacity: 0, y: 40 }"
        :whileInView="{ opacity: 1, y: 0, transition: { duration: 0.7, ease: 'easeOut' } }"
        :inViewOptions="{ once: true, amount: 0.2 }"
        class="max-w-2xl mx-auto"
      >
        <div class="text-center mb-12">
          <span class="inline-block text-sm font-semibold text-green-700 bg-green-50 px-4 py-1.5 rounded-full mb-4 tracking-wide uppercase">Acesso antecipado</span>
          <h2 class="text-3xl sm:text-4xl lg:text-5xl font-extrabold text-gray-900 leading-tight">
            Quer ser um dos primeiros a usar o
            <span class="text-green-600">Agro Controle?</span>
          </h2>
          <p class="mt-4 text-lg text-gray-500">
            Deixe seu contato e receba acesso antecipado. Vagas limitadas para a versão beta.
          </p>
        </div>

        <!-- Success state -->
        <div v-if="submitted" class="bg-green-50 border-2 border-green-200 rounded-2xl p-12 text-center">
          <div class="w-16 h-16 bg-green-100 rounded-full flex items-center justify-center mx-auto mb-6">
            <CheckCircleIcon class="w-10 h-10 text-green-600" />
          </div>
          <h3 class="text-2xl font-bold text-green-900 mb-2">Cadastro realizado!</h3>
          <p class="text-green-700">
            Obrigado, {{ form.name }}! Entraremos em contato em breve com seu acesso ao beta.
          </p>
        </div>

        <!-- Form -->
        <form v-else @submit.prevent="handleSubmit" class="bg-white rounded-2xl shadow-xl shadow-gray-200/50 border border-gray-100 p-8 sm:p-12">
          <div class="space-y-6">
            <div>
              <label for="name" class="block text-sm font-semibold text-gray-700 mb-2">
                Nome completo
              </label>
              <div class="relative">
                <UserIcon class="absolute left-3 top-1/2 -translate-y-1/2 w-5 h-5 text-gray-400 pointer-events-none z-10" />
                <InputText
                  id="name"
                  v-model="form.name"
                  placeholder="Seu nome"
                  class="w-full !pl-11"
                  required
                />
              </div>
            </div>

            <div>
              <label for="email" class="block text-sm font-semibold text-gray-700 mb-2">
                E-mail
              </label>
              <div class="relative">
                <EnvelopeIcon class="absolute left-3 top-1/2 -translate-y-1/2 w-5 h-5 text-gray-400 pointer-events-none z-10" />
                <InputText
                  id="email"
                  v-model="form.email"
                  type="email"
                  placeholder="seu@email.com"
                  class="w-full !pl-11"
                  required
                />
              </div>
            </div>

            <div>
              <label for="phone" class="block text-sm font-semibold text-gray-700 mb-2">
                Telefone / WhatsApp
              </label>
              <div class="relative">
                <PhoneIcon class="absolute left-3 top-1/2 -translate-y-1/2 w-5 h-5 text-gray-400 pointer-events-none z-10" />
                <InputText
                  id="phone"
                  v-model="form.phone"
                  placeholder="(00) 00000-0000"
                  class="w-full !pl-11"
                  required
                />
              </div>
            </div>

            <Button
              type="submit"
              :label="loading ? 'Enviando...' : 'Garantir meu acesso'"
              :loading="loading"
              class="!w-full !py-4 !text-lg !font-bold !bg-green-600 hover:!bg-green-700 !border-none !rounded-xl !shadow-lg !shadow-green-600/20"
            />
          </div>
        </form>

        <!-- Trust badges -->
        <div class="mt-8 flex flex-wrap items-center justify-center gap-6">
          <div
            v-for="(item, i) in trustItems"
            :key="i"
            class="flex items-center gap-2 text-sm text-gray-500"
          >
            <component :is="item.icon" class="w-4 h-4 text-green-600" />
            <span>{{ item.text }}</span>
          </div>
        </div>
      </Motion>
    </div>
  </section>
</template>
