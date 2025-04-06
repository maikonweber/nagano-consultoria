<script>
  const servicos = {
    consignado: {
      titulo: "Empréstimo Consignado",
      descricao: "Empréstimo com desconto direto na folha de pagamento, oferecendo as menores taxas do mercado.",
      taxaJuros: {
        minima: 1.3,
        maxima: 2.1
      },
      prazos: {
        minimo: 12,
        maximo: 96
      },
      beneficios: [
        "Menores taxas do mercado",
        "Parcelas fixas",
        "Desconto em folha",
        "Sem consulta ao SPC/Serasa",
        "Aprovação facilitada"
      ],
      documentosNecessarios: [
        "RG e CPF",
        "Comprovante de residência",
        "Contracheque dos últimos 3 meses",
        "Dados bancários"
      ]
    },
    creditoPessoal: {
      titulo: "Crédito Pessoal",
      descricao: "Solução rápida e descomplicada para suas necessidades financeiras.",
      taxaJuros: {
        minima: 2.5,
        maxima: 4.8
      },
      prazos: {
        minimo: 6,
        maximo: 48
      },
      beneficios: [
        "Aprovação rápida",
        "Sem alienação de bens",
        "Flexibilidade no uso do dinheiro",
        "Parcelas fixas"
      ],
      documentosNecessarios: [
        "RG e CPF",
        "Comprovante de residência",
        "Comprovante de renda",
        "Dados bancários"
      ]
    },
    refinanciamento: {
      titulo: "Refinanciamento",
      descricao: "Melhore as condições do seu empréstimo atual com taxas mais atrativas.",
      taxaJuros: {
        minima: 1.8,
        maxima: 3.2
      },
      prazos: {
        minimo: 12,
        maximo: 72
      },
      beneficios: [
        "Unificação de dívidas",
        "Redução do valor da parcela",
        "Melhores taxas",
        "Prazo estendido"
      ],
      documentosNecessarios: [
        "RG e CPF",
        "Comprovante de residência",
        "Contrato atual do empréstimo",
        "Comprovante de renda"
      ]
    },
    aposentados: {
      titulo: "Empréstimo para Aposentados",
      descricao: "Condições especiais para aposentados e pensionistas do INSS.",
      taxaJuros: {
        minima: 1.5,
        maxima: 2.3
      },
      prazos: {
        minimo: 12,
        maximo: 84
      },
      beneficios: [
        "Taxas especiais para aposentados",
        "Desconto direto no benefício",
        "Sem consulta ao SPC/Serasa",
        "Atendimento preferencial"
      ],
      documentosNecessarios: [
        "RG e CPF",
        "Comprovante de residência",
        "Extrato do benefício",
        "Dados bancários"
      ]
    }
  };
</script>

<svelte:head>
  <title>Serviços - Nagano Consultoria</title>
  <meta name="description" content="Conheça nossos serviços financeiros com as melhores taxas do mercado. Empréstimo consignado, crédito pessoal e mais.">
</svelte:head>

<div class="bg-[#e3e1dd] min-h-screen py-20">
  <div class="container mx-auto px-4">
    <h1 class="text-4xl md:text-5xl font-bold text-[#0d1c24] text-center mb-12">
      Nossos Serviços
    </h1>
    
    <div class="grid gap-8">
      {#each Object.entries(servicos) as [key, servico]}
        <div class="bg-white rounded-lg shadow-lg overflow-hidden">
          <div class="bg-[#0d1c24] p-6">
            <h2 class="text-2xl font-bold text-[#e3e1dd]">{servico.titulo}</h2>
            <p class="text-[#b5b6b7] mt-2">{servico.descricao}</p>
          </div>
          
          <div class="p-6">
            <div class="grid md:grid-cols-2 gap-6">
              <div>
                <h3 class="text-xl font-semibold text-[#6c7c7e] mb-4">Taxas de Juros</h3>
                <div class="bg-[#e3e1dd] rounded-lg p-4">
                  <p class="text-[#0d1c24]">
                    A partir de <span class="font-bold text-2xl">{servico.taxaJuros.minima}%</span> ao mês
                  </p>
                  <p class="text-[#8c8f91] text-sm">
                    Até {servico.taxaJuros.maxima}% ao mês*
                  </p>
                </div>
                
                <h3 class="text-xl font-semibold text-[#6c7c7e] mt-6 mb-4">Prazos</h3>
                <div class="bg-[#e3e1dd] rounded-lg p-4">
                  <p class="text-[#0d1c24]">
                    De {servico.prazos.minimo} até {servico.prazos.maximo} meses
                  </p>
                </div>
              </div>
              
              <div>
                <h3 class="text-xl font-semibold text-[#6c7c7e] mb-4">Benefícios</h3>
                <ul class="space-y-2">
                  {#each servico.beneficios as beneficio}
                    <li class="flex items-center text-[#8c8f91]">
                      <svg class="w-5 h-5 text-[#6c7c7e] mr-2" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
                      </svg>
                      {beneficio}
                    </li>
                  {/each}
                </ul>
                
                <h3 class="text-xl font-semibold text-[#6c7c7e] mt-6 mb-4">Documentos Necessários</h3>
                <ul class="space-y-2">
                  {#each servico.documentosNecessarios as documento}
                    <li class="flex items-center text-[#8c8f91]">
                      <svg class="w-5 h-5 text-[#6c7c7e] mr-2" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z" />
                      </svg>
                      {documento}
                    </li>
                  {/each}
                </ul>
              </div>
            </div>
            
            <div class="mt-8 text-center">
              <a href="/contato" class="inline-block bg-[#6c7c7e] text-[#e3e1dd] px-8 py-3 rounded-full text-lg font-semibold hover:bg-[#74746c] transition-colors">
                Solicitar {servico.titulo}
              </a>
            </div>
          </div>
        </div>
      {/each}
    </div>
    
    <p class="text-[#8c8f91] text-sm mt-8 text-center">
      * As taxas podem variar de acordo com o perfil do cliente, prazo e condições do serviço escolhido.
      Entre em contato para uma análise personalizada.
    </p>
  </div>
</div>

<style>
  :global(body) {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }
</style>
