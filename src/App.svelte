<script>
  import Nav from './lib/Nav.svelte';
  import Card from './lib/Card.svelte'
 
</script>
<Nav />
<main>
  

  <h2>We appreciate your feedback to help improve our services</h2>

  <div class="card">
    <Card />
  </div>

</main>

<style>

  main{
    width: 100%;
    height: 80vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
  }


</style>
