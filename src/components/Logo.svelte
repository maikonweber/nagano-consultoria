<script>
  export let width = "200";
  export let height = "200";
</script>

<div class="logo-container">
  <img 
    src="/logo.png" 
    alt="Nagano Consultoria Logo" 
    {width}
    {height}
    class="logo-image"
  />
</div>

<style>
  .logo-container {
    display: flex;
    justify-content: center;
    align-items: center;
  }
  
  .logo-image {
    max-width: 100%;
    height: auto;
    object-fit: contain;
  }
</style> 