<script>
  export let message
  export let subMessage
  import { fly, fade } from 'svelte/transition';
  import gif from '../assets/giphy.gif'
</script>
<div in:fly="{{ y: 200, duration: 2000, delay: 800 }}" out:fly="{{ y: -200, duration: 800 }}">

<img src={gif} alt="Thank you bag" />
<h2>{message}</h2>
<p>{subMessage}</p>

</div>


<style>
  p{
    line-height: 1.5;
  }
</style>