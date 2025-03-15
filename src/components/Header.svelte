<script>
  import { onMount } from 'svelte';
  
  let isMenuOpen = false;
  let isScrolled = false;
  
  function toggleMenu() {
    isMenuOpen = !isMenuOpen;
  }
  
  onMount(() => {
    const handleScroll = () => {
      isScrolled = window.scrollY > 50;
    };
    
    window.addEventListener('scroll', handleScroll);
    
    return () => {
      window.removeEventListener('scroll', handleScroll);
    };
  });
</script>

<header class={`fixed top-0 left-0 w-full z-50 transition-all duration-300 ${isScrolled ? 'bg-white/95 shadow-md py-2' : 'bg-white py-4'}`}>
  <div class="container mx-auto px-4 flex justify-between items-center">
    <div class="flex-shrink-0">
      <a href="/" class="block">
        <img src="/images/logo.svg" alt="Nagano Consultoria" class={`transition-all duration-300 ${isScrolled ? 'h-10' : 'h-12'}`} />
      </a>
    </div>
    
    <button 
      class="md:hidden flex flex-col justify-center items-center p-2 focus:outline-none" 
      on:click={toggleMenu}
      aria-label="Toggle menu"
    >
      <span class="w-6 h-0.5 bg-gray-800 mb-1.5 transition-all"></span>
      <span class="w-6 h-0.5 bg-gray-800 mb-1.5 transition-all"></span>
      <span class="w-6 h-0.5 bg-gray-800 transition-all"></span>
    </button>
    
    <nav class={`absolute md:relative top-full left-0 w-full md:w-auto bg-white md:bg-transparent shadow-lg md:shadow-none transition-all duration-300 ${isMenuOpen ? 'opacity-100 translate-y-0' : 'opacity-0 -translate-y-full md:opacity-100 md:translate-y-0'} md:block`}>
      <ul class="flex flex-col md:flex-row py-4 md:py-0">
        <li class="px-4 py-2 md:py-0"><a href="/" class="text-gray-800 hover:text-blue-600 font-medium transition-colors">Início</a></li>
        <li class="px-4 py-2 md:py-0"><a href="/servicos" class="text-gray-800 hover:text-blue-600 font-medium transition-colors">Serviços</a></li>
        <li class="px-4 py-2 md:py-0"><a href="/sobre" class="text-gray-800 hover:text-blue-600 font-medium transition-colors">Sobre Nós</a></li>
        <li class="px-4 py-2 md:py-0"><a href="/blog" class="text-gray-800 hover:text-blue-600 font-medium transition-colors">Blog</a></li>
        <li class="px-4 py-2 md:py-0"><a href="/contato" class="text-gray-800 hover:text-blue-600 font-medium transition-colors">Contato</a></li>
      </ul>
    </nav>
    
    <div class="hidden md:block">
      <a href="/contato" class="bg-blue-600 hover:bg-blue-700 text-white font-medium py-2 px-4 rounded shadow-md hover:shadow-lg transition-all transform hover:-translate-y-0.5">
        Solicitar Consulta
      </a>
    </div>
  </div>
</header>