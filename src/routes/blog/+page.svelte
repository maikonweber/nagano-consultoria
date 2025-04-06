<svelte:head>
  <title>Blog Nagano - Dicas Financeiras</title>
  <meta name="description" content="Blog da Nagano Consultoria com artigos sobre finanças, empréstimos e dicas financeiras para CLT.">
  <meta name="keywords" content="Blog financeiro, Dicas financeiras, Empréstimo consignado, Finanças pessoais">
  <meta name="author" content="Nagano Consultoria">
</svelte:head>

<script>
  import { onMount } from 'svelte';
  import { fade } from 'svelte/transition';
  import MainLayout from '../../components/MainLayout.svelte';
  import Logo from '../../components/Logo.svelte';
  
  /**
	 * @type {any[]}
	 */
  let posts = [];
  let loading = true;
  
  // Formato de dados esperado
  // {
  //     "id": 2,
  //     "titulo": "Como usar o empréstimo consignado de forma inteligente",
  //     "img": "https://example.com/image.jpg",
  //     "text": "<p>Conteúdo completo</p>",
  //     "preview": "Breve resumo do artigo...",
  //     "created_at": "2025-03-26T19:20:58.762Z",
  //     "deleted_at": null
  // }

  async function fetchPosts() {
    try {
      // URL do endpoint seria substituído pelo endpoint real
      const response = await fetch('https://api.naganoconsultoria.com.br/blog/');
      const data = await response.json();
      
      // Mapeamento dos dados recebidos
      posts = data.map((/** @type {{ titulo: any; img: any; preview: any; created_at: string | number | Date; id: { toString: () => any; }; text: any; }} */ post) => ({
        title: post.titulo || 'Sem título',
        image: post.img || '/images/placeholder-blog.jpg',
        excerpt: post.preview || 'Sem prévia disponível',
        date: new Date(post.created_at).toLocaleDateString('pt-BR'),
        slug: post.id.toString(),
        text: post.text || ''
      }));
      
    } catch (error) {
      console.error('Erro ao carregar posts:', error);
      // Dados de fallback para demonstração
      posts = [
        {
          title: 'Como usar o empréstimo consignado de forma inteligente',
          image: '/images/blog-consignado.jpg',
          excerpt: 'Aprenda a utilizar o empréstimo consignado para alavancar sua vida financeira sem cair em armadilhas.',
          date: '05/04/2025',
          slug: '1'
        },
        {
          title: 'Refinanciamento: quando vale a pena?',
          image: '/images/blog-refinanciamento.jpg',
          excerpt: 'Descubra os momentos certos para refinanciar suas dívidas e economizar com juros menores.',
          date: '28/03/2025',
          slug: '2'
        },
        {
          title: 'Planejamento financeiro para trabalhadores CLT',
          image: '/images/blog-planejamento.jpg',
          excerpt: 'Um guia completo para organizar suas finanças aproveitando as vantagens do regime CLT.',
          date: '15/03/2025',
          slug: '3'
        }
      ];
    } finally {
      loading = false;
    }
  }

  onMount(fetchPosts);
</script>

<MainLayout title="Blog Nagano - Dicas Financeiras">
  <div class="blog-hero-section bg-[#0d1c24] py-16">
    <div class="container mx-auto px-4">
      <div class="flex flex-col items-center text-center">
        <Logo width="200" height="200" />
        <h1 class="text-3xl md:text-4xl font-bold text-[#e3e1dd] mt-6 mb-4">
          Blog Nagano Consultoria
        </h1>
        <p class="text-xl text-[#b5b6b7] max-w-2xl">
          Dicas, informações e conteúdo relevante para sua saúde financeira
        </p>
      </div>
    </div>
  </div>

  <section class="py-16 bg-[#e3e1dd]">
    <div class="container mx-auto px-4">
      {#if loading}
        <div class="flex justify-center items-center py-12">
          <div class="loader"></div>
          <p class="ml-4 text-[#0d1c24] font-medium">Carregando artigos...</p>
        </div>
      {:else}
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
          {#each posts as post}
            <article 
              class="bg-white rounded-lg shadow-md overflow-hidden transition-all duration-300 hover:shadow-xl transform hover:-translate-y-1"
              in:fade={{ duration: 300, delay: 150 }}
            >
              <div class="post-image h-48 overflow-hidden">
                <img 
                  src={post.image} 
                  alt={post.title} 
                  class="w-full h-full object-cover transition-transform duration-500 hover:scale-105"
                />
              </div>
              <div class="p-6">
                <span class="text-sm text-[#74746c] font-medium block mb-2">{post.date}</span>
                <h2 class="text-2xl font-bold text-[#0d1c24] mb-3">{post.title}</h2>
                <p class="text-[#8c8f91] mb-4">{post.excerpt}</p>
                <a 
                  href={`/blog/${post.slug}`} 
                  class="inline-block bg-[#6c7c7e] text-[#e3e1dd] px-4 py-2 rounded-md font-medium transition-colors hover:bg-[#74746c]"
                >
                  Ler mais
                </a>
              </div>
            </article>
          {/each}
        </div>
      {/if}
    </div>
  </section>

  <section class="py-16 bg-[#0d1c24] text-[#e3e1dd]">
    <div class="container mx-auto px-4 text-center">
      <h2 class="text-3xl font-bold mb-4">Tem alguma dúvida sobre finanças?</h2>
      <p class="text-xl text-[#b5b6b7] mb-8 max-w-2xl mx-auto">
        Nossa equipe de consultores financeiros está pronta para ajudar você a tomar as melhores decisões para seu futuro.
      </p>
      <a 
        href="/contato" 
        class="inline-block bg-[#6c7c7e] text-[#e3e1dd] px-8 py-3 rounded-full text-lg font-semibold hover:bg-[#74746c] transition-colors"
      >
        Fale com um Especialista
      </a>
    </div>
  </section>
</MainLayout>

<style>
  .loader {
    border: 4px solid rgba(108, 124, 126, 0.3);
    border-radius: 50%;
    border-top: 4px solid #6c7c7e;
    width: 30px;
    height: 30px;
    animation: spin 1s linear infinite;
  }
  
  @keyframes spin {
    0% { transform: rotate(0deg); }
    100% { transform: rotate(360deg); }
  }
</style>