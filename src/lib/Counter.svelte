<script>
  let clicked = false
  const updateClicked = () => {
    clicked = !clicked
  }
  
</script>
<button on:click={updateClicked}>Begin</button>
{clicked}
{#if clicked}
  <h3>hello world</h3>

{/if}