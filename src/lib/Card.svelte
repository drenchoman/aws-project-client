<script>
  import {clicked} from './Stores'
  const updateClicked = () => {
    clicked.set(true)
  }
  
</script>

{#if !$clicked}
<button on:click={updateClicked}>Begin</button>

{/if}