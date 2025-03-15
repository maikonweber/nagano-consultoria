<section class="features">
  <div class="container">
    <h2 class="section-title">Por que escolher a Nagano</h2>
    <div class="features-grid">
      <div class="feature">
        <div class="feature-icon">✓</div>
        <h3>Melhores Taxas</h3>
        <p>Trabalhamos com as menores taxas do mercado, garantindo mais economia para você.</p>
      </div>
      <div class="feature">
        <div class="feature-icon">⚡</div>
        <h3>Agilidade</h3>
        <p>Aprovação rápida e liberação do dinheiro em até 24 horas após a assinatura.</p>
      </div>
      <div class="feature">
        <div class="feature-icon">🔒</div>
        <h3>Segurança</h3>
        <p>Seus dados são tratados com total segurança e confidencialidade.</p>
      </div>
    </div>
  </div>
</section>

<style>
  .features {
    padding: 4rem 0;
    background-color: var(--white);
  }
  
  .features-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 2rem;
  }
  
  .feature {
    background: linear-gradient(135deg, var(--white), var(--light-color));
    padding: 2rem;
    border-radius: 10px;
    text-align: center;
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
    transition: all 0.3s ease;
  }
  
  .feature:hover {
    transform: translateY(-10px);
    box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);
  }
  
  .feature-icon {
    width: 60px;
    height: 60px;
    margin: 0 auto 1rem;
    background-color: var(--secondary-color);
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    color: var(--white);
    font-size: 1.5rem;
  }
  
  .feature h3 {
    font-size: 1.3rem;
    margin-bottom: 1rem;
    color: var(--primary-color);
  }
</style>