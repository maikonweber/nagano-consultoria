<svelte:head>
  <title>Nagano Consultoria - Soluções em Empréstimos e Crédito</title>
  <meta name="description" content="Nagano Consultoria oferece as melhores soluções em empréstimos consignados e não consignados para CLT. Taxas competitivas, atendimento personalizado e aprovação rápida.">
  <meta name="keywords" content="Empréstimo consignado, Empréstimo pessoal, Crédito CLT, Consultoria financeira, Empréstimo sem consignação, Crédito pessoal, Financiamento, Crédito rápido, Melhores taxas">
  <meta name="author" content="Nagano Consultoria">
  
  

  <!-- Open Graph / Facebook -->
  <meta property="og:type" content="website">
  <meta property="og:url" content="https://naganoconsultoria.com.br/logo.png">
  <meta property="og:title" content="Nagano Consultoria Financeira - Especialistas em Empréstimos">
  <meta property="og:description" content="Soluções personalizadas em empréstimos consignados e não consignados para trabalhadores CLT. Análise de crédito gratuita, taxas reduzidas e aprovação rápida.">
  <meta property="og:image" content="https://naganoconsultoria.com.br/images/og-image.jpg">
  
  <!-- Twitter -->
  <meta property="twitter:card" content="summary_large_image">
  <meta property="twitter:url" content="https://naganoconsultoria.com.br/logo.png">
  <meta property="twitter:title" content="Nagano Consultoria - Crédito Facilitado para CLT">
  <meta property="twitter:description" content="Simplifique sua vida financeira com nossas soluções de crédito para trabalhadores CLT. Empréstimos consignados com as melhores condições do mercado.">
  <meta property="twitter:image" content="https://naganoconsultoria.com.br/images/twitter-image.jpg">
  
  <!-- Metadados adicionais -->
  <meta name="robots" content="index, follow">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="language" content="Portuguese">
  <meta name="revisit-after" content="7 days">
  <meta name="geo.region" content="BR">
  
  <!-- Metadados específicos para empréstimos -->
  <meta name="service:type" content="financial">
  <meta name="service:category" content="loans, credit, financial consulting">
  <meta name="service:audience" content="clt employees, formal workers">
  <meta name="service:benefit" content="lower rates, quick approval, personalized solutions">
  
  <!-- Microdata para Rich Snippets -->
  <script type="application/ld+json">
    {
      "@context": "https://schema.org",
      "@type": "FinancialService",
      "name": "Nagano Consultoria",
      "description": "Especialistas em soluções de crédito e empréstimos para trabalhadores CLT",
      "url": "https://naganoconsultoria.com.br",
      "telephone": "+55-XX-XXXX-XXXX",
      "address": {
        "@type": "PostalAddress",
        "streetAddress": "Avenida Principal, 1000",
        "addressLocality": "São Paulo",
        "addressRegion": "SP",
        "postalCode": "01000-000",
        "addressCountry": "BR"
      },
      "geo": {
        "@type": "GeoCoordinates",
        "latitude": "-23.550520",
        "longitude": "-46.633308"
      },
      "openingHours": "Mo,Tu,We,Th,Fr 09:00-18:00",
      "sameAs": [
        "https://www.facebook.com/naganoconsultoria",
        "https://www.instagram.com/naganoconsultoria",
        "https://www.linkedin.com/company/naganoconsultoria"
      ],
      "priceRange": "$$"
    }
  </script>
</svelte:head>


<script>
  import MainLayout from '../components/MainLayout.svelte';
  import Hero from '../components/Hero.svelte';
  import ServiceCard from '../components/ServiceCard.svelte';
  import TestimonialCard from '../components/TestimonialCard.svelte';
  import LoanCalculator from '../components/LoanCalculator.svelte';
  import CTASection from '../components/CTASection.svelte';
  import Logo from '../components/Logo.svelte';
  
  const services = [
    {
      title: 'Empréstimo Consignado',
      description: 'Taxas reduzidas e parcelas descontadas diretamente da folha de pagamento.',
      icon: 'dollar-sign',
      link: '/servicos/'
    },
    {
      title: 'Crédito Pessoal',
      description: 'Solução rápida para suas necessidades financeiras com processo simplificado.',
      icon: 'credit-card',
      link: '/servicos/'
    },
    {
      title: 'Refinanciamento',
      description: 'Melhore as condições do seu empréstimo atual com taxas mais atrativas.',
      icon: 'refresh-cw',
      link: '/servicos/'
    },
    {
      title: 'Consultoria Financeira',
      description: 'Orientação especializada para organizar suas finanças e planejar o futuro.',
      icon: 'trending-up',
      link: '/servicos/'
    },
    {
      title: 'Empréstimo Consignado Aposentadoria',
      description: 'Empréstimo sem necessidade de consignação de salário.',
      icon: 'credit-card',
      link: '/servicos/'
    }
  ];
  
  const testimonials = [
    {
      name: 'Carlos Silva',
      position: 'Professor',
      content: 'A Nagano me ajudou a conseguir um empréstimo com taxa muito menor do que eu encontrava no mercado. Processo rápido e atendimento excelente!',
      rating: 5
    },
    {
      name: 'Ana Oliveira',
      position: 'Enfermeira',
      content: 'Precisava de dinheiro com urgência para uma emergência médica. A equipe da Nagano foi ágil e em 48h o valor já estava na minha conta.',
      rating: 5
    },
    {
      name: 'Roberto Almeida',
      position: 'Funcionário Público',
      content: 'Consultoria séria e transparente. Me ajudaram a escolher a melhor opção de crédito para minha situação, sem surpresas ou taxas ocultas.',
      rating: 4
    }
  ];
</script>

<MainLayout title="Nagano Consultoria - Soluções em Empréstimos e Crédito">
  <div class="hero-section bg-[#0d1c24] py-20">
    <div class="container mx-auto px-4">
      <div class="flex flex-col items-center text-center">
        <Logo width="300" height="300" />
        <h1 class="text-4xl md:text-5xl font-bold text-[#e3e1dd] mt-8 mb-4">
          Soluções em Empréstimos para Trabalhadores CLT
        </h1>
        <p class="text-xl text-[#b5b6b7] max-w-3xl">
          Taxas reduzidas, aprovação rápida e atendimento personalizado
        </p>
        <a href="#calculadora" class="mt-8 bg-[#6c7c7e] text-[#e3e1dd] px-8 py-3 rounded-full text-lg font-semibold hover:bg-[#74746c] transition-colors">
          Simule Agora
        </a>
      </div>
    </div>
  </div>

  <section id="servicos" class="py-20 bg-[#e3e1dd]">
    <div class="container mx-auto px-4">
      <h2 class="text-3xl md:text-4xl font-bold text-center text-[#0d1c24] mb-12">
        Nossos Serviços
      </h2>
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
        {#each services as service}
          <ServiceCard {...service} />
        {/each}
      </div>
    </div>
  </section>

  <section id="calculadora" class="py-20 bg-[#e3e1dd]">
    <div class="container mx-auto px-4">
      <h2 class="text-3xl md:text-4xl font-bold text-center text-[#0d1c24] mb-12">
        Simule Seu Empréstimo
      </h2>
      <div class="max-w-4xl mx-auto">
        <LoanCalculator />
      </div>
    </div>
  </section>

  <section id="vantagens" class="py-20 bg-[#0d1c24]">
    <div class="container mx-auto px-4">
      <div class="text-center mb-12">
        <h2 class="text-3xl md:text-4xl font-bold text-[#e3e1dd] mb-4">Por que escolher a Nagano?</h2>
        <p class="text-xl text-[#b5b6b7] max-w-3xl mx-auto">
          Somos especialistas em encontrar as melhores condições para você
        </p>
      </div>
      
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
        <div class="bg-[#e3e1dd] rounded-lg p-6 shadow-md hover:shadow-xl transition-all duration-300 transform hover:-translate-y-1 text-center">
          <div class="text-4xl text-[#6c7c7e] mb-4 flex justify-center">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-16 w-16" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 8c-1.657 0-3 .895-3 2s1.343 2 3 2 3 .895 3 2-1.343 2-3 2m0-8c1.11 0 2.08.402 2.599 1M12 8V7m0 1v8m0 0v1m0-1c-1.11 0-2.08-.402-2.599-1M21 12a9 9 0 11-18 0 9 9 0 0118 0z" />
            </svg>
          </div>
          <h3 class="text-xl font-semibold text-[#0d1c24] mb-3">Taxas Competitivas</h3>
          <p class="text-[#8c8f91]">Negociamos com as principais instituições financeiras para garantir as melhores taxas do mercado.</p>
        </div>
        
        <div class="bg-[#e3e1dd] rounded-lg p-6 shadow-md hover:shadow-xl transition-all duration-300 transform hover:-translate-y-1 text-center">
          <div class="text-4xl text-[#6c7c7e] mb-4 flex justify-center">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-16 w-16" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 10V3L4 14h7v7l9-11h-7z" />
            </svg>
          </div>
          <h3 class="text-xl font-semibold text-[#0d1c24] mb-3">Aprovação Rápida</h3>
          <p class="text-[#8c8f91]">Nosso processo ágil permite aprovação em até 24 horas para a maioria dos casos.</p>
        </div>
        
        <div class="bg-[#e3e1dd] rounded-lg p-6 shadow-md hover:shadow-xl transition-all duration-300 transform hover:-translate-y-1 text-center">
          <div class="text-4xl text-[#6c7c7e] mb-4 flex justify-center">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-16 w-16" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 20h5v-2a3 3 0 00-5.356-1.857M17 20H7m10 0v-2c0-.656-.126-1.283-.356-1.857M7 20H2v-2a3 3 0 015.356-1.857M7 20v-2c0-.656.126-1.283.356-1.857m0 0a5.002 5.002 0 019.288 0M15 7a3 3 0 11-6 0 3 3 0 016 0zm6 3a2 2 0 11-4 0 2 2 0 014 0zM7 10a2 2 0 11-4 0 2 2 0 014 0z" />
            </svg>
          </div>
          <h3 class="text-xl font-semibold text-[#0d1c24] mb-3">Atendimento Personalizado</h3>
          <p class="text-[#8c8f91]">Analisamos sua situação para recomendar a melhor solução financeira para você.</p>
        </div>
        
        <div class="bg-[#e3e1dd] rounded-lg p-6 shadow-md hover:shadow-xl transition-all duration-300 transform hover:-translate-y-1 text-center">
          <div class="text-4xl text-[#6c7c7e] mb-4 flex justify-center">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-16 w-16" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z" />
            </svg>
          </div>
          <h3 class="text-xl font-semibold text-[#0d1c24] mb-3">Transparência Total</h3>
          <p class="text-[#8c8f91]">Sem taxas ocultas ou surpresas. Você sabe exatamente quanto vai pagar desde o início.</p>
        </div>
      </div>
    </div>
  </section>
  
  <section id="depoimentos" class="py-20 bg-[#e3e1dd]">
    <div class="container mx-auto px-4">
      <div class="text-center mb-12">
        <h2 class="text-3xl md:text-4xl font-bold text-[#0d1c24] mb-4">O que nossos clientes dizem</h2>
        <p class="text-xl text-[#8c8f91] max-w-3xl mx-auto">
          A satisfação de nossos clientes é nossa melhor recomendação
        </p>
      </div>
      
      <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
        {#each testimonials as testimonial}
          <TestimonialCard {...testimonial} />
        {/each}
      </div>
    </div>
  </section>
  
  <section class="py-20 bg-[#0d1c24] text-[#e3e1dd]">
    <div class="container mx-auto px-4 text-center">
      <h2 class="text-3xl md:text-4xl font-bold mb-4">Pronto para resolver sua situação financeira?</h2>
      <p class="text-xl text-[#b5b6b7] mb-8">Nossos consultores estão à disposição para ajudar você a encontrar a melhor solução.</p>
      <a href="/contato" class="inline-block bg-[#6c7c7e] text-[#e3e1dd] px-8 py-3 rounded-full text-lg font-semibold hover:bg-[#74746c] transition-colors">
        Fale com um Consultor
      </a>
    </div>
  </section>
</MainLayout>

<style>
  :global(body) {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
  }
</style>