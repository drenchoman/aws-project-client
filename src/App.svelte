<script>
  import Nav from './lib/Nav.svelte';
  import Counter from './lib/Counter.svelte'
</script>
<Nav />
<main>


  <h2>We appreciate your feedback to help improve our services</h2>

  <div class="card">
    <Counter />
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
