<script>
  import {clicked, counter} from './Stores'
  const updateClicked = () => {
    clicked.set(true)
    counter.update(n => n + 1)
  }
  
</script>

{#if !$clicked}
<button on:click={updateClicked}>Sure</button>

{/if}