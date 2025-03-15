<script>
  import { onMount } from 'svelte';
  
  let loanAmount = 5000;
  let loanTerm = 24;
  let interestRate = 1.5;
  let monthlyPayment = 0;
  let totalPayment = 0;
  let totalInterest = 0;
  
  $: {
    calculateLoan();
  }
  
  function calculateLoan() {
    // Convert annual rate to monthly rate and decimal
    const monthlyRate = interestRate / 100;
    
    // Calculate monthly payment
    if (monthlyRate === 0) {
      monthlyPayment = loanAmount / loanTerm;
    } else {
      monthlyPayment = (loanAmount * monthlyRate * Math.pow(1 + monthlyRate, loanTerm)) / 
                       (Math.pow(1 + monthlyRate, loanTerm) - 1);
    }
    
    totalPayment = monthlyPayment * loanTerm;
    totalInterest = totalPayment - loanAmount;
  }
  
  // Format currency
  function formatCurrency(value) {
    return new Intl.NumberFormat('pt-BR', {
      style: 'currency',
      currency: 'BRL'
    }).format(value);
  }
  
  onMount(() => {
    calculateLoan();
  });
</script>

<div class="bg-white rounded-lg shadow-xl overflow-hidden flex flex-wrap">
  <!-- Formulário -->
  <div class="w-full lg:w-1/2 p-6 md:p-8">
    <div class="mb-6">
      <label for="loan-amount" class="block text-gray-700 font-medium mb-2">Valor do Empréstimo</label>
      <div>
        <input 
          type="range" 
          id="loan-amount" 
          bind:value={loanAmount} 
          min="1000" 
          max="50000" 
          step="1000"
          class="w-full h-2 bg-gray-200 rounded-lg appearance-none cursor-pointer accent-blue-600"
        >
        <div class="mt-2 text-right font-semibold text-gray-700">{formatCurrency(loanAmount)}</div>
      </div>
    </div>
    
    <div class="mb-6">
      <label for="loan-term" class="block text-gray-700 font-medium mb-2">Prazo (meses)</label>
      <div>
        <input 
          type="range" 
          id="loan-term" 
          bind:value={loanTerm} 
          min="6" 
          max="60" 
          step="6"
          class="w-full h-2 bg-gray-200 rounded-lg appearance-none cursor-pointer accent-blue-600"
        >
        <div class="mt-2 text-right font-semibold text-gray-700">{loanTerm} meses</div>
      </div>
    </div>
    
    <div class="mb-6">
      <label for="interest-rate" class="block text-gray-700 font-medium mb-2">Taxa de Juros (% ao mês)</label>
      <div>
        <input 
          type="range" 
          id="interest-rate" 
          bind:value={interestRate} 
          min="0.5" 
          max="5" 
          step="0.1"
          class="w-full h-2 bg-gray-200 rounded-lg appearance-none cursor-pointer accent-blue-600"
        >
        <div class="mt-2 text-right font-semibold text-gray-700">{interestRate.toFixed(1)}% a.m.</div>
      </div>
    </div>
  </div>
  
  <!-- Resultados -->
  <div class="w-full lg:w-1/2 bg-blue-600 p-6 md:p-8 text-white">
    <div class="mb-4">
      <div class="text-lg font-normal mb-1">Parcela Mensal</div>
      <div class="text-3xl font-bold">{formatCurrency(monthlyPayment)}</div>
    </div>
    
    <div class="mb-4">
      <div class="text-lg font-normal mb-1">Total a Pagar</div>
      <div class="text-3xl font-bold">{formatCurrency(totalPayment)}</div>
    </div>
    
    <div class="mb-8">
      <div class="text-lg font-normal mb-1">Total em Juros</div>
      <div class="text-3xl font-bold">{formatCurrency(totalInterest)}</div>
    </div>
    
    <a 
      href="/contato" 
      class="block text-center bg-white text-blue-600 hover:bg-gray-100 font-semibold py-3 rounded-md transition-colors"
    >
      Solicitar este empréstimo
    </a>
  </div>
</div>