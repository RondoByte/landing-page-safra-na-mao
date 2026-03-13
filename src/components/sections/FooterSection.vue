<script setup>
const currentYear = new Date().getFullYear()
const githubUrl = 'https://github.com/Schambin/Agro-Controle-Landing-Page'
</script>

<template>
  <footer class="bg-gray-900 text-gray-400">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-16">
      <div class="grid md:grid-cols-3 gap-12">
        <!-- Brand -->
        <div>
          <div class="flex items-center gap-3 mb-4">
            <div class="w-10 h-10 bg-green-600 rounded-xl flex items-center justify-center">
              <span class="text-white font-bold text-lg">A</span>
            </div>
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
              <a :href="githubUrl" target="_blank" rel="noopener" class="hover:text-green-400 transition-colors">
                GitHub
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
          <a
            :href="githubUrl"
            target="_blank"
            rel="noopener"
            class="inline-flex items-center gap-2 text-sm text-green-400 hover:text-green-300 transition-colors"
          >
            <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24"><path d="M12 0C5.37 0 0 5.37 0 12c0 5.31 3.435 9.795 8.205 11.385.6.105.825-.255.825-.57 0-.285-.015-1.23-.015-2.235-3.015.555-3.795-.735-4.035-1.41-.135-.345-.72-1.41-1.23-1.695-.42-.225-1.02-.78-.015-.795.945-.015 1.62.87 1.845 1.23 1.08 1.815 2.805 1.305 3.495.99.105-.78.42-1.305.765-1.605-2.67-.3-5.46-1.335-5.46-5.925 0-1.305.465-2.385 1.23-3.225-.12-.3-.54-1.53.12-3.18 0 0 1.005-.315 3.3 1.23.96-.27 1.98-.405 3-.405s2.04.135 3 .405c2.295-1.56 3.3-1.23 3.3-1.23.66 1.65.24 2.88.12 3.18.765.84 1.23 1.905 1.23 3.225 0 4.605-2.805 5.625-5.475 5.925.435.375.81 1.095.81 2.22 0 1.605-.015 2.895-.015 3.3 0 .315.225.69.825.57A12.02 12.02 0 0024 12c0-6.63-5.37-12-12-12z"/></svg>
            Ver no GitHub
          </a>
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
