<script>
  export let services = [];
</script>

<section class="services" id="servicos">
  <div class="container">
    <h2 class="section-title">Nossos Serviços</h2>
    <div class="services-grid">
      {#each services as service}
        <div class="service">
          <img src={service.imageUrl} alt={service.title} class="service-img">
          <div class="service-content">
            <h3>{service.title}</h3>
            <p>{service.description}</p>
          </div>
        </div>
      {/each}
    </div>
  </div>
</section>

<style>
  .services {
    padding: 4rem 0;
    background-color: var(--light-gray);
  }
  
  .services-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 2rem;
  }
  
  .service {
    background-color: var(--white);
    border-radius: 10px;
    overflow: hidden;
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
    transition: all 0.3s ease;
  }
  
  .service:hover {
    transform: translateY(-10px);
    box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);
  }
  
  .service-img {
    width: 100%;
    height: 200px;
    object-fit: cover;
  }
  
  .service-content {
    padding: 1.5rem;
  }
  
  .service h3 {
    font-size: 1.3rem;
    margin-bottom: 1rem;
    color: var(--primary-color);
  }
</style>