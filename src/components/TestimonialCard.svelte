<script>
  export let name;
  export let position;
  export let content;
  export let rating;
  
  // Cria um array com base na classificação para exibir as estrelas
  $: stars = Array.from({ length: 5 }, (_, i) => i < rating);
</script>

<div class="bg-white rounded-lg p-6 shadow-md hover:shadow-lg transition-all">
  <!-- Conteúdo do depoimento -->
  <p class="text-gray-600 mb-4 italic">"{content}"</p>
  
  <!-- Estrelas de classificação -->
  <div class="flex mb-4">
    {#each stars as filled}
      <svg 
        xmlns="http://www.w3.org/2000/svg" 
        class={`h-5 w-5 ${filled ? 'text-yellow-500' : 'text-gray-300'}`}
        viewBox="0 0 20 20" 
        fill="currentColor"
      >
        <path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
      </svg>
    {/each}
  </div>
  
  <!-- Informações do cliente -->
  <div class="flex items-center">
    <div class="w-12 h-12 bg-gray-300 rounded-full flex items-center justify-center text-gray-600 font-bold text-xl">
      {name.charAt(0)}
    </div>
    <div class="ml-3">
      <h4 class="text-gray-800 font-semibold">{name}</h4>
      <p class="text-gray-500 text-sm">{position}</p>
    </div>
  </div>
</div>