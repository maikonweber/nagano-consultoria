<svelte:head>
  <title>Contato - Nagano Consultoria</title>
  <meta name="description" content="Entre em contato com a Nagano Consultoria. Estamos prontos para ajudar você a encontrar a melhor solução financeira.">
</svelte:head>

<div class="bg-[#e3e1dd] min-h-screen py-20">
  <div class="container mx-auto px-4">
    <h1 class="text-4xl md:text-5xl font-bold text-[#0d1c24] text-center mb-12">
      Fale Conosco
    </h1>

    <div class="grid md:grid-cols-2 gap-12 max-w-6xl mx-auto">
      <!-- Formulário de Contato -->
      <div class="bg-white rounded-lg shadow-lg p-8">
        <h2 class="text-2xl font-bold text-[#0d1c24] mb-6">Envie sua Mensagem</h2>
        
        <form class="space-y-6">
          <div>
            <label class="block text-[#6c7c7e] mb-2">Nome Completo</label>
            <input type="text" class="w-full p-3 border border-[#b5b6b7] rounded-lg focus:outline-none focus:ring-2 focus:ring-[#6c7c7e]">
          </div>

          <div>
            <label class="block text-[#6c7c7e] mb-2">E-mail</label>
            <input type="email" class="w-full p-3 border border-[#b5b6b7] rounded-lg focus:outline-none focus:ring-2 focus:ring-[#6c7c7e]">
          </div>

          <div>
            <label class="block text-[#6c7c7e] mb-2">Telefone</label>
            <input type="tel" class="w-full p-3 border border-[#b5b6b7] rounded-lg focus:outline-none focus:ring-2 focus:ring-[#6c7c7e]">
          </div>

          <div>
            <label class="block text-[#6c7c7e] mb-2">Assunto</label>
            <select class="w-full p-3 border border-[#b5b6b7] rounded-lg focus:outline-none focus:ring-2 focus:ring-[#6c7c7e]">
              <option>Selecione um assunto</option>
              <option>Empréstimo Consignado</option>
              <option>Crédito Pessoal</option>
              <option>Refinanciamento</option>
              <option>Outros</option>
            </select>
          </div>

          <div>
            <label class="block text-[#6c7c7e] mb-2">Mensagem</label>
            <textarea rows="5" class="w-full p-3 border border-[#b5b6b7] rounded-lg focus:outline-none focus:ring-2 focus:ring-[#6c7c7e]"></textarea>
          </div>

          <button class="w-full bg-[#6c7c7e] text-[#e3e1dd] px-8 py-3 rounded-full text-lg font-semibold hover:bg-[#74746c] transition-colors">
            Enviar Mensagem
          </button>
        </form>
      </div>

      <!-- Informações de Contato -->
      <div class="space-y-8">
        <!-- Dados de Contato -->
        <div class="bg-white rounded-lg shadow-lg p-8">
          <h2 class="text-2xl font-bold text-[#0d1c24] mb-6">Nossos Contatos</h2>
          
          <div class="space-y-4">
            <div class="flex items-center">
              <div class="bg-[#e3e1dd] p-3 rounded-full mr-4">
                <svg class="w-6 h-6 text-[#6c7c7e]" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z"/>
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z"/>
                </svg>
              </div>
              <div>
                <p class="text-[#0d1c24] font-semibold">Endereço</p>
                <p class="text-[#8c8f91]">Av. Paulista, 1234 - São Paulo/SP</p>
              </div>
            </div>

            <div class="flex items-center">
              <div class="bg-[#e3e1dd] p-3 rounded-full mr-4">
                <svg class="w-6 h-6 text-[#6c7c7e]" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z"/>
                </svg>
              </div>
              <div>
                <p class="text-[#0d1c24] font-semibold">Telefone</p>
                <p class="text-[#8c8f91]">(11) 9999-9999</p>
              </div>
            </div>

            <div class="flex items-center">
              <div class="bg-[#e3e1dd] p-3 rounded-full mr-4">
                <svg class="w-6 h-6 text-[#6c7c7e]" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"/>
                </svg>
              </div>
              <div>
                <p class="text-[#0d1c24] font-semibold">E-mail</p>
                <p class="text-[#8c8f91]">contato@naganoconsultoria.com.br</p>
              </div>
            </div>

            <div class="flex items-center">
              <div class="bg-[#e3e1dd] p-3 rounded-full mr-4">
                <svg class="w-6 h-6 text-[#6c7c7e]" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z"/>
                </svg>
              </div>
              <div>
                <p class="text-[#0d1c24] font-semibold">Atendimento</p>
                <p class="text-[#8c8f91]">Seg-Sex: 08h às 18h</p>
                <p class="text-[#8c8f91]">Sábado: 08h às 12h</p>
              </div>
            </div>
          </div>
        </div>

        <!-- Redes Sociais -->
        <div class="bg-white rounded-lg shadow-lg p-8">
          <h2 class="text-2xl font-bold text-[#0d1c24] mb-6">Redes Sociais</h2>
          
          <div class="flex space-x-4 justify-center">
            <a href="#" class="bg-[#e3e1dd] p-3 rounded-full hover:bg-[#d4d2ce] transition-colors">
              <svg class="w-6 h-6 text-[#6c7c7e]" fill="currentColor" viewBox="0 0 24 24">
                <path d="M24 4.557c-.883.392-1.832.656-2.828.775 1.017-.609 1.798-1.574 2.165-2.724-.951.564-2.005.974-3.127 1.195-.897-.957-2.178-1.555-3.594-1.555-3.179 0-5.515 2.966-4.797 6.045-4.091-.205-7.719-2.165-10.148-5.144-1.29 2.213-.669 5.108 1.523 6.574-.806-.026-1.566-.247-2.229-.616-.054 2.281 1.581 4.415 3.949 4.89-.693.188-1.452.232-2.224.084.626 1.956 2.444 3.379 4.6 3.419-2.07 1.623-4.678 2.348-7.29 2.04 2.179 1.397 4.768 2.212 7.548 2.212 9.142 0 14.307-7.721 13.995-14.646.962-.695 1.797-1.562 2.457-2.549z"/>
              </svg>
            </a>

            <a href="#" class="bg-[#e3e1dd] p-3 rounded-full hover:bg-[#d4d2ce] transition-colors">
              <svg class="w-6 h-6 text-[#6c7c7e]" fill="currentColor" viewBox="0 0 24 24">
                <path d="M12 0c-6.627 0-12 5.373-12 12s5.373 12 12 12 12-5.373 12-12-5.373-12-12-12zm3 8h-1.35c-.538 0-.65.221-.65.778v1.222h2l-.209 2h-1.791v7h-3v-7h-2v-2h2v-2.308c0-1.769.931-2.692 3.029-2.692h1.971v3z"/>
              </svg>
            </a>

            <a href="#" class="bg-[#e3e1dd] p-3 rounded-full hover:bg-[#d4d2ce] transition-colors">
              <svg class="w-6 h-6 text-[#6c7c7e]" fill="currentColor" viewBox="0 0 24 24">
                <path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"/>
              </svg>
            </a>

            <a href="#" class="bg-[#e3e1dd] p-3 rounded-full hover:bg-[#d4d2ce] transition-colors">
              <svg class="w-6 h-6 text-[#6c7c7e]" fill="currentColor" viewBox="0 0 24 24">
                <path d="M4.98 3.5c0 1.381-1.11 2.5-2.48 2.5s-2.48-1.119-2.48-2.5c0-1.38 1.11-2.5 2.48-2.5s2.48 1.12 2.48 2.5zm.02 4.5h-5v16h5v-16zm7.982 0h-4.968v16h4.969v-8.399c0-4.67 6.029-5.052 6.029 0v8.399h4.988v-10.131c0-7.88-8.922-7.593-11.018-3.714v-2.155z"/>
              </svg>
            </a>
          </div>
        </div>

        <!-- Mapa -->
        <div class="bg-white rounded-lg shadow-lg overflow-hidden">
          <iframe 
            src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3657.3764159163437!2d-46.65882292544108!3d-23.554930778819873!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x94ce582b483c6d65%3A0x6200d1a3d52b7428!2sAv.%20Paulista%2C%201234%20-%20Bela%20Vista%2C%20S%C3%A3o%20Paulo%20-%20SP%2C%2001310-100!5e0!3m2!1spt-BR!2sbr!4v1716328521424!5m2!1spt-BR!2sbr"
            width="100%"
            height="300"
            style="border:0;"
            allowfullscreen=""
            loading="lazy"
            referrerpolicy="no-referrer-when-downgrade">
          </iframe>
        </div>
      </div>
    </div>
  </div>
</div>

<style>
  :global(body) {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
  }
</style>