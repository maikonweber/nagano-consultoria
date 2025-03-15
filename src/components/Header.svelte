<script>
  import { onMount } from 'svelte';
  
  let mobileMenuOpen = false;
  
  function toggleMobileMenu() {
    mobileMenuOpen = !mobileMenuOpen;
  }
  
  // Fecha o menu móvel quando clica em um link do menu
  function closeMenu() {
    mobileMenuOpen = false;
  }
  
  // Fecha o menu móvel quando a tela é redimensionada para tamanho maior
  onMount(() => {
    const handleResize = () => {
      if (window.innerWidth > 768) {
        mobileMenuOpen = false;
      }
    };
    
    window.addEventListener('resize', handleResize);
    
    return () => {
      window.removeEventListener('resize', handleResize);
    };
  });
</script>

<header>
  <div class="container">
    <div class="header-container">
      <a href="/" class="logo">
        <div class="logo-img"></div>
        Nagano Consignados
      </a>
      
      <button class="mobile-toggle" on:click={toggleMobileMenu} aria-label="Toggle menu">
        ☰
      </button>
      
      <nav class:active={mobileMenuOpen}>
        <ul>
          <li><a href="/" on:click={closeMenu}>Início</a></li>
          <li><a href="#servicos" on:click={closeMenu}>Serviços</a></li>
          <li><a href="#blog" on:click={closeMenu}>Blog</a></li>
          <li><a href="#videos" on:click={closeMenu}>Vídeos</a></li>
          <li><a href="#contato" on:click={closeMenu}>Contato</a></li>
        </ul>
      </nav>
    </div>
  </div>
</header>

<style>
  header {
    background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
    color: var(--white);
    padding: 1rem 0;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
    position: sticky;
    top: 0;
    z-index: 1000;
  }
  
  .header-container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    position: relative;
  }
  
  .logo {
    font-size: 1.8rem;
    font-weight: 700;
    color: var(--white);
    text-decoration: none;
    display: flex;
    align-items: center;
  }
  
  .logo-img {
    width: 40px;
    height: 40px;
    margin-right: 10px;
    background-color: var(--white);
    border-radius: 50%;
  }
  
  nav ul {
    display: flex;
    list-style: none;
    margin: 0;
    padding: 0;
  }
  
  nav ul li {
    margin-left: 1.5rem;
  }
  
  nav ul li a {
    color: var(--white);
    text-decoration: none;
    font-weight: 500;
    transition: all 0.3s ease;
  }
  
  nav ul li a:hover {
    color: var(--light-color);
  }
  
  .mobile-toggle {
    display: none;
    background: none;
    border: none;
    color: var(--white);
    font-size: 1.5rem;
    cursor: pointer;
  }
  
  @media (max-width: 768px) {
    .header-container {
      flex-direction: column;
      align-items: flex-start;
    }
    
    nav {
      width: 100%;
      display: none;
      margin-top: 1rem;
    }
    
    nav.active {
      display: block;
    }
    
    nav ul {
      flex-direction: column;
    }
    
    nav ul li {
      margin: 0;
      margin-bottom: 1rem;
    }
    
    .mobile-toggle {
      display: block;
      position: absolute;
      top: 0.5rem;
      right: 0;
    }
  }
</style>