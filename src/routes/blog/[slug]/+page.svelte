<svelte:head>
  {#if postData && postData.title}
    <title>{postData.title} - Nagano Consultoria</title>
    <meta name="description" content={postData.excerpt}>
    <meta property="og:title" content={`${postData.title} - Nagano Consultoria`}>
    <meta property="og:description" content={postData.excerpt}>
    <meta property="og:image" content={postData.image || 'https://naganoconsultoria.com.br/images/og-default.jpg'}>
    <meta property="og:url" content={`https://naganoconsultoria.com.br/blog/${slug}`}>
  {:else}
    <title>Blog - Nagano Consultoria</title>
    <meta name="description" content="Artigos e conteúdos sobre finanças pessoais, empréstimos e dicas para CLT.">
  {/if}
  <meta name="keywords" content="Empréstimo consignado, Finanças pessoais, Crédito, Consultoria financeira">
  <meta name="author" content="Nagano Consultoria">
</svelte:head>

<script>
// @ts-nocheck

  import { onMount } from 'svelte';
  import { fade } from 'svelte/transition';
  import MainLayout from '../../../components/MainLayout.svelte';
  import Logo from '../../../components/Logo.svelte';
  
  let slug = '';
  /**
	 * @type {{ title: any; excerpt: any; image: any; date: any; content: any; } | null}
	 */
  let postData = null;
  let loading = true;
  let error = false;
  let errorMessage = '';
  
  /**
	 * @param {string} text
	 */
  function getExcerpt(text, maxLength = 150) {
    if (!text) return '';
    // Remove HTML tags se houver
    const plainText = text.replace(/<[^>]*>/g, '');
    return plainText.length > maxLength 
      ? plainText.slice(0, maxLength) + '...' 
      : plainText;
  }
  
  async function fetchPostData() {
    try {
      // URL do endpoint seria substituído pelo endpoint real
      const response = await fetch(`https://api.naganoconsultoria.com.br/blog/${slug}`);
      
      if (!response.ok) {
        throw new Error(response.status === 404 
          ? 'Artigo não encontrado' 
          : `Erro ${response.status}: ${response.statusText}`);
      }
      
      const data = await response.json();
      
      postData = {
        title: data.titulo || 'Sem título',
        image: data.img || '/images/placeholder-blog.jpg',
        excerpt: getExcerpt(data.preview || data.text),
        date: new Date(data.created_at).toLocaleDateString('pt-BR'),
        content: data.text || '<p>Conteúdo indisponível</p>'
      };
      
    } catch (err) {
      console.error('Erro ao carregar post:', err);
      error = true;
      // @ts-ignore
      errorMessage = err.message || 'Erro ao carregar o artigo';
      
      // Para demonstração, criamos dados fictícios se o endpoint falhar
      if (!error) {
      
        postData = {
          title: 'Como usar o empréstimo consignado de forma inteligente',
          image: '/images/blog-consignado.jpg',
          excerpt: 'Aprenda a utilizar o empréstimo consignado para alavancar sua vida financeira sem cair em armadilhas.',
          date: '05/04/2025',
          content: `
            <p>O empréstimo consignado é uma das modalidades de crédito mais vantajosas disponíveis para trabalhadores com carteira assinada, funcionários públicos e aposentados. Com taxas de juros significativamente menores que outras opções no mercado, essa modalidade de crédito pode ser uma ferramenta poderosa quando utilizada com sabedoria.</p>
            
            <h2>Entendendo o Empréstimo Consignado</h2>
            
            <p>No empréstimo consignado, as parcelas são descontadas diretamente da folha de pagamento ou do benefício previdenciário, o que reduz o risco para os bancos e, consequentemente, permite a oferta de taxas mais atrativas. No entanto, essa facilidade também pode levar a decisões precipitadas.</p>
            
            <h2>Quando Vale a Pena?</h2>
            
            <p>O empréstimo consignado é indicado para:</p>
            <ul>
              <li>Quitar dívidas mais caras, como cartão de crédito ou cheque especial</li>
              <li>Realizar investimentos com retorno superior ao custo do empréstimo</li>
              <li>Lidar com emergências médicas ou situações imprevisíveis</li>
              <li>Financiar educação ou qualificação profissional</li>
            </ul>
            
            <h2>Cuidados Importantes</h2>
            
            <p>Antes de contratar, certifique-se de:</p>
            <ul>
              <li>Comparar as taxas oferecidas por diferentes instituições</li>
              <li>Calcular o impacto da parcela no seu orçamento mensal</li>
              <li>Verificar se o prazo e o valor das parcelas são adequados</li>
              <li>Ler atentamente todas as cláusulas do contrato</li>
            </ul>
            
            <p>Lembre-se: o empréstimo consignado compromete parte da sua renda por um período considerável. Portanto, é fundamental ter clareza sobre os objetivos do crédito e como ele se encaixa no seu planejamento financeiro a longo prazo.</p>
            
            <h2>Conclusão</h2>
            
            <p>O empréstimo consignado, quando bem utilizado, pode ser um aliado para organizar as finanças ou realizar projetos importantes. O segredo está em usar esse recurso de forma estratégica, considerando sempre o impacto futuro nas suas finanças.</p>
            
            <p>Se tiver dúvidas sobre empréstimo consignado ou quiser analisar qual a melhor opção para o seu caso, entre em contato com um de nossos consultores. Estamos aqui para ajudar você a tomar as melhores decisões financeiras!</p>
          `
        };
      }
    } finally {
      loading = false;
    }
  }
  
  onMount(() => {
    // Extrair o slug da URL
    const pathParts = window.location.pathname.split('/');
    slug = pathParts[pathParts.length - 1];
    
    if (!slug) {
      error = true;
      errorMessage = 'URL inválida';
      loading = false;
    } else {
      fetchPostData();
    }
  });
</script>

<MainLayout title={postData ? postData.title : 'Blog - Nagano Consultoria'}>
  <div class="bg-[#0d1c24] py-12">
    <div class="container mx-auto px-4">
      <div class="flex items-center justify-center">
        <a href="/blog" class="flex items-center text-[#e3e1dd] hover:text-[#b5b6b7] transition-colors">
          <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 mr-2" viewBox="0 0 20 20" fill="currentColor">
            <path fill-rule="evenodd" d="M9.707 16.707a1 1 0 01-1.414 0l-6-6a1 1 0 010-1.414l6-6a1 1 0 011.414 1.414L5.414 9H17a1 1 0 110 2H5.414l4.293 4.293a1 1 0 010 1.414z" clip-rule="evenodd" />
          </svg>
          <span>Voltar para o Blog</span>
        </a>
      </div>
    </div>
  </div>

  <div class="bg-[#e3e1dd] py-12 min-h-screen">
    <div class="container mx-auto px-4">
      {#if loading}
        <div class="flex justify-center items-center py-12">
          <div class="loader"></div>
          <p class="ml-4 text-[#0d1c24] font-medium">Carregando artigo...</p>
        </div>
      {:else if error}
        <div 
          class="bg-red-50 border-l-4 border-red-500 p-6 rounded-lg shadow-md max-w-3xl mx-auto"
          in:fade={{ duration: 300 }}
        >
          <div class="flex items-center">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-red-500 mr-3" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 8v4m0 4h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z" />
            </svg>
            <h2 class="text-xl font-bold text-red-700">{errorMessage}</h2>
          </div>
          <p class="mt-3 text-red-600">Não foi possível carregar o artigo solicitado.</p>
          <div class="mt-6">
            <a 
              href="/blog" 
              class="inline-block bg-[#6c7c7e] text-[#e3e1dd] px-4 py-2 rounded-md font-medium transition-colors hover:bg-[#74746c]"
            >
              Voltar para o Blog
            </a>
          </div>
        </div>
      {:else}
        <article 
          class="bg-white rounded-lg shadow-md overflow-hidden max-w-4xl mx-auto"
          in:fade={{ duration: 400 }}
        >
          {#if postData.image}
            <div class="h-64 md:h-80 overflow-hidden">
              <img 
                src={postData.image} 
                alt={postData.title} 
                class="w-full h-full object-cover"
              />
            </div>
          {/if}
          
          <div class="p-6 md:p-8">
            <div class="mb-6">
              <span class="text-sm text-[#74746c] font-medium">{postData.date}</span>
              <h1 class="text-3xl md:text-4xl font-bold text-[#0d1c24] mt-2">{postData.title}</h1>
            </div>
            
            <div class="post-content prose prose-lg max-w-none">
              {@html postData.content}
            </div>
            
            <div class="mt-12 pt-6 border-t border-gray-200">
              <div class="flex flex-col md:flex-row md:items-center md:justify-between">
                <div class="mb-4 md:mb-0">
                  <h3 class="text-lg font-semibold text-[#0d1c24]">Gostou deste artigo?</h3>
                  <p class="text-[#8c8f91]">Compartilhe com quem precisa dessas informações</p>
                </div>
                <div class="flex space-x-4">
                  <a href="#" class="text-gray-500 hover:text-blue-600" aria-label="Compartilhar no Facebook">
                    <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24" aria-hidden="true">
                      <path fill-rule="evenodd" d="M22 12c0-5.523-4.477-10-10-10S2 6.477 2 12c0 4.991 3.657 9.128 8.438 9.878v-6.987h-2.54V12h2.54V9.797c0-2.506 1.492-3.89 3.777-3.89 1.094 0 2.238.195 2.238.195v2.46h-1.26c-1.243 0-1.63.771-1.63 1.562V12h2.773l-.443 2.89h-2.33v6.988C18.343 21.128 22 16.991 22 12z" clip-rule="evenodd"></path>
                    </svg>
                  </a>
                  <a href="#" class="text-gray-500 hover:text-blue-400" aria-label="Compartilhar no Twitter">
                    <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24" aria-hidden="true">
                      <path d="M8.29 20.251c7.547 0 11.675-6.253 11.675-11.675 0-.178 0-.355-.012-.53A8.348 8.348 0 0022 5.92a8.19 8.19 0 01-2.357.646 4.118 4.118 0 001.804-2.27 8.224 8.224 0 01-2.605.996 4.107 4.107 0 00-6.993 3.743 11.65 11.65 0 01-8.457-4.287 4.106 4.106 0 001.27 5.477A4.072 4.072 0 012.8 9.713v.052a4.105 4.105 0 003.292 4.022 4.095 4.095 0 01-1.853.07 4.108 4.108 0 003.834 2.85A8.233 8.233 0 012 18.407a11.616 11.616 0 006.29 1.84"></path>
                    </svg>
                  </a>
                  <a href="#" class="text-gray-500 hover:text-blue-600" aria-label="Compartilhar no LinkedIn">
                    <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24" aria-hidden="true">
                      <path fill-rule="evenodd" d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z" clip-rule="evenodd"></path>
                    </svg>
                  </a>
                  <a href="#" class="text-gray-500 hover:text-green-600" aria-label="Compartilhar no WhatsApp">
                    <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24" aria-hidden="true">
                      <path fill-rule="evenodd" d="M20.283 3.567c-2.242-2.243-5.215-3.486-8.395-3.56C5.546.069.07 5.544.069 11.886c0 2.195.578 4.347 1.669 6.236L.068 24l6.064-1.593a11.937 11.937 0 005.734 1.459h.004c6.332 0 11.808-5.152 11.818-11.485.01-3.067-1.18-5.96-3.373-8.143l-.032-.031zM11.888 21.788h-.004c-1.715 0-3.407-.461-4.883-1.331l-.35-.208-3.616.948.965-3.527-.229-.363a9.833 9.833 0 01-1.508-5.25c0-5.45 4.436-9.886 9.889-9.886 2.643.002 5.125 1.031 6.991 2.898s2.889 4.349 2.885 6.991c-.01 5.454-4.445 9.886-9.896 9.886h-.004v.009-.009l.002-.001zm5.43-7.387c-.295-.147-1.75-.865-2.021-.965-.271-.098-.469-.147-.669.147-.197.298-.771.965-.946 1.164-.173.197-.35.221-.644.073-.295-.147-1.262-.465-2.402-1.483-.887-.79-1.488-1.768-1.661-2.066-.175-.297-.019-.459.13-.607.137-.131.295-.342.444-.513.148-.172.197-.294.296-.491.099-.2.048-.37-.024-.518-.075-.147-.671-1.615-.919-2.21-.245-.582-.49-.502-.669-.512-.173-.009-.37-.011-.569-.011-.197 0-.518.074-.79.37-.271.3-1.039.99-1.039 2.458s1.063 2.851 1.211 3.049c.148.195 2.055 3.387 5.094 4.622.341.148.626.24.839.306.369.119.705.101.97.061.296-.044 1.063-.434 1.211-1.106.022-.661.169-1.213.094-1.358-.075-.147-.443-.221-.739-.369" clip-rule="evenodd"></path>
                    </svg>
                  </a>
                </div>
              </div>
            </div>
            
            <div class="mt-10 pt-8 border-t border-gray-200">
              <div class="flex flex-wrap justify-between items-center">
                <a 
                  href="/blog" 
                  class="inline-block bg-[#6c7c7e] text-[#e3e1dd] px-4 py-2 rounded-md font-medium transition-colors hover:bg-[#74746c] mb-4 md:mb-0"
                >
                  Voltar para o Blog
                </a>
                <a 
                  href="/contato" 
                  class="inline-block bg-[#0d1c24] text-[#e3e1dd] px-4 py-2 rounded-md font-medium transition-colors hover:bg-[#2e3b42]"
                >
                  Fale com um Consultor
                </a>
              </div>
            </div>
          </div>
        </article>
      {/if}
    </div>
  </div>
  
  <section class="py-16 bg-[#0d1c24] text-[#e3e1dd]">
    <div class="container mx-auto px-4 text-center">
      <h2 class="text-3xl font-bold mb-4">Precisa de ajuda com suas finanças?</h2>
      <p class="text-xl text-[#b5b6b7] mb-8 max-w-2xl mx-auto">
        Nossa equipe está pronta para oferecer as melhores soluções financeiras para você.
      </p>
      <a 
        href="/contato" 
        class="inline-block bg-[#6c7c7e] text-[#e3e1dd] px-8 py-3 rounded-full text-lg font-semibold hover:bg-[#74746c] transition-colors"
      >
        Entre em Contato
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
  
  :global(.post-content h2) {
    font-size: 1.75rem;
    font-weight: 700;
    color: #0d1c24;
    margin-top: 2rem;
    margin-bottom: 1rem;
  }
  
  :global(.post-content p) {
    margin-bottom: 1.25rem;
    color: #4b4b4b;
    line-height: 1.7;
  }
  
  :global(.post-content ul),
  :global(.post-content ol) {
    margin-bottom: 1.5rem;
    margin-left: 1.5rem;
  }
  
  :global(.post-content li) {
    margin-bottom: 0.5rem;
    color: #4b4b4b;
  }
  
  :global(.post-content a) {
    color: #6c7c7e;
    text-decoration: underline;
    transition: color 0.2s;
  }
  
  :global(.post-content a:hover) {
    color: #0d1c24;
  }
  
  :global(.post-content blockquote) {
    border-left: 4px solid #6c7c7e;
    padding-left: 1rem;
    font-style: italic;
    color: #666;
    margin: 1
  }

</style>
