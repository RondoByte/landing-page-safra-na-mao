<script setup>
const currentYear = new Date().getFullYear()
</script>

<template>
  <footer class="bg-gray-900 text-gray-400">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-16">
      <div class="grid md:grid-cols-3 gap-12">
        <!-- Brand -->
        <div>
          <div class="flex items-center gap-3 mb-4">
            <img src="../../../public/favicon.jpeg" alt="Agro Controle" class="w-10 h-10 rounded-xl" />
            <div>
              <h3 class="text-white font-bold text-lg">Agro Controle</h3>
              <p class="text-xs text-gray-500">Gestão rural simplificada</p>
            </div>
          </div>
          <p class="text-sm leading-relaxed">
            App de gestão rural que coloca o controle da sua propriedade na palma da mão. Produção, finanças e clima em um único lugar.
          </p>
        </div>

        <!-- Links -->
        <div>
          <h4 class="text-white font-semibold mb-4">Navegação</h4>
          <ul class="space-y-3 text-sm">
            <li><a href="#features" class="hover:text-green-400 transition-colors">Funcionalidades</a></li>
            <li><a href="#lead-form" class="hover:text-green-400 transition-colors">Acesso antecipado</a></li>
            <li>
              <a
                href="https://safranamao.vercel.app/"
                target="_blank"
                rel="noopener noreferrer"
                class="hover:text-green-400 transition-colors inline-flex items-center gap-1.5"
              >
                Entrar no sistema
                <svg xmlns="http://www.w3.org/2000/svg" class="w-3.5 h-3.5" viewBox="0 0 20 20" fill="currentColor">
                  <path fill-rule="evenodd" d="M5.22 14.78a.75.75 0 001.06 0l7.22-7.22v5.69a.75.75 0 001.5 0v-7.5a.75.75 0 00-.75-.75h-7.5a.75.75 0 000 1.5h5.69l-7.22 7.22a.75.75 0 000 1.06z" clip-rule="evenodd" />
                </svg>
              </a>
            </li>
          </ul>
        </div>

        <!-- Hackathon -->
        <div>
          <h4 class="text-white font-semibold mb-4">Sobre o projeto</h4>
          <p class="text-sm leading-relaxed mb-4">
            Projeto desenvolvido para apresentação em hackathon. Focado em resolver problemas reais da gestão rural com tecnologia acessível.
          </p>
        </div>
      </div>

      <div class="mt-12 pt-8 border-t border-gray-800 flex flex-col sm:flex-row items-center justify-between gap-4">
        <p class="text-sm">
          &copy; {{ currentYear }} Agro Controle. Todos os direitos reservados.
        </p>
      </div>
    </div>
  </footer>
</template>
