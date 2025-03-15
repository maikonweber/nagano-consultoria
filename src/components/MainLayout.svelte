<script>
  import Header from './Header.svelte';
  import Footer from './Footer.svelte';
  
  import { onMount } from 'svelte';

  export let title = "Nagano Consultoria - Soluções em Empréstimos e Crédito";
  
  onMount(() => {
    // Scripts que precisam ser executados após o carregamento da página
  });
</script>

<svelte:head>
  <title>{title}</title>
</svelte:head>

<div class="flex flex-col min-h-screen">
  <Header />
  
  <main class="flex-grow">
    <slot />
  </main>
  
  <Footer />
</div>