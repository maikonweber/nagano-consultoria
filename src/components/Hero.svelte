<script>
  export let title = "Soluções em Empréstimos para Trabalhadores CLT";
  export let subtitle = "Taxas reduzidas, aprovação rápida e atendimento personalizado";
  export let ctaText = "Simule Agora";
  export let ctaLink = "#calculadora";
  export let image = "/images/hero-image.jpg";
</script>

<section class="relative h-screen min-h-[600px] max-h-[800px] w-full text-white">
  <!-- Imagem de fundo com overlay -->
  <div class="absolute inset-0 z-0">
    <div class="absolute inset-0 bg-gradient-to-b from-black/50 to-black/70 z-10"></div>
    <img 
      src={image} 
      alt="Hero background" 
      class="w-full h-full object-cover object-center brightness-75"
    />
  </div>
  
  <!-- Conteúdo -->
  <div class="relative z-20 h-full flex items-center">
    <div class="container mx-auto px-4">
      <div class="max-w-2xl">
        <h1 class="text-4xl md:text-5xl font-bold mb-4 leading-tight">{title}</h1>
        <p class="text-xl md:text-2xl mb-8">{subtitle}</p>
        <a 
          href={ctaLink} 
          class="inline-block bg-blue-600 hover:bg-blue-700 text-white font-semibold text-lg py-3 px-8 rounded-md shadow-lg hover:shadow-xl transition-all transform hover:-translate-y-1"
        >
          {ctaText}
        </a>
      </div>
    </div>
  </div>
</section>