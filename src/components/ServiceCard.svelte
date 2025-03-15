<script>
  export let title;
  export let description;
  export let icon;
  export let link;
</script>

<div class="bg-white rounded-lg p-6 shadow-md hover:shadow-xl transition-all duration-300 transform hover:-translate-y-1 h-full flex flex-col">
  <div class="text-4xl text-blue-600 mb-4">
    <i class="feather-{icon}"></i>
  </div>
  
  <h3 class="text-xl font-semibold text-gray-800 mb-3">{title}</h3>
  
  <p class="text-gray-600 mb-5 flex-grow">{description}</p>
  
  <a href={link} class="inline-flex items-center text-blue-600 font-medium hover:text-blue-800 transition-colors group">
    Saiba mais
    <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 ml-1 transform transition-transform group-hover:translate-x-1" fill="none" viewBox="0 0 24 24" stroke="currentColor">
      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14 5l7 7m0 0l-7 7m7-7H3" />
    </svg>
  </a>
</div>