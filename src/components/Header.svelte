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

<header class={`fixed top-0 left-0 w-full z-50 transition-all duration-300 ${isScrolled ? 'bg-[#F5F5DC]/95 shadow-md py-2' : 'bg-[#F5F5DC] py-4'}`}>
  <div class="container mx-auto px-4 flex justify-between items-center">
    <div class="flex-shrink-0">
      <a href="/" class="block">
        <img src="/logo.png" alt="Nagano Consultoria" class={`transition-all duration-300 ${isScrolled ? 'h-10' : 'h-12'}`} />
      </a>
    </div>
    
    <button 
      class="md:hidden flex flex-col justify-center items-center p-2 focus:outline-none" 
      on:click={toggleMenu}
      aria-label="Toggle menu"
    >
      <span class="w-6 h-0.5 bg-[#000080] mb-1.5 transition-all"></span>
      <span class="w-6 h-0.5 bg-[#000080] mb-1.5 transition-all"></span>
      <span class="w-6 h-0.5 bg-[#000080] transition-all"></span>
    </button>
    
    <nav class={`absolute md:relative top-full left-0 w-full md:w-auto bg-[#F5F5DC] md:bg-transparent shadow-lg md:shadow-none transition-all duration-300 ${isMenuOpen ? 'opacity-100 translate-y-0' : 'opacity-0 -translate-y-full md:opacity-100 md:translate-y-0'} md:block`}>
      <ul class="flex flex-col md:flex-row py-4 md:py-0">
        <li class="px-4 py-2 md:py-0"><a href="/" class="text-[#000080] hover:text-[#000080]/80 font-medium transition-colors">Início</a></li>
        <li class="px-4 py-2 md:py-0"><a href="/servicos" class="text-[#000080] hover:text-[#000080]/80 font-medium transition-colors">Serviços</a></li>
        <li class="px-4 py-2 md:py-0"><a href="/blog" class="text-[#000080] hover:text-[#000080]/80 font-medium transition-colors">Blog</a></li>
        <li class="px-4 py-2 md:py-0"><a href="/finance-help" class="text-[#000080] hover:text-[#000080]/80 font-medium transition-colors">Finance Help</a></li>
        <li class="px-4 py-2 md:py-0"><a href="/sobre" class="text-[#000080] hover:text-[#000080]/80 font-medium transition-colors">Sobre Nós</a></li>
        <li class="px-4 py-2 md:py-0"><a href="/contato" class="text-[#000080] hover:text-[#000080]/80 font-medium transition-colors">Contato</a></li>
      </ul>
    </nav>
    
    <div class="hidden md:block">
      <a href="/contato" class="bg-[#000080] hover:bg-[#000080]/90 text-[#F5F5DC] font-medium py-2 px-4 rounded shadow-md hover:shadow-lg transition-all transform hover:-translate-y-0.5">
        Solicitar Consulta
      </a>
    </div>
  </div>
</header>