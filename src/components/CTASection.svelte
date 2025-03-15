<script>
  export let title = "Pronto para resolver sua situação financeira?";
  export let subtitle = "Nossos consultores estão à disposição para ajudar você a encontrar a melhor solução.";
  export let buttonText = "Fale com um Consultor";
  export let buttonLink = "/contato";
</script>

<section class="bg-blue-600 py-16 md:py-20">
  <div class="container mx-auto px-4 text-center">
    <h2 class="text-3xl md:text-4xl font-bold text-white mb-4">{title}</h2>
    
    <p class="text-xl text-blue-100 max-w-3xl mx-auto mb-8">{subtitle}</p>
    
    <a 
      href={buttonLink} 
      class="inline-block bg-white text-blue-600 hover:bg-blue-50 font-bold py-3 px-8 rounded-md shadow-md hover:shadow-lg transition-all transform hover:-translate-y-1"
    >
      {buttonText}
    </a>
  </div>
</section>