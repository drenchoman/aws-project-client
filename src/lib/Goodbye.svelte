<script>
  export let message
  export let subMessage
  import { fly, fade } from 'svelte/transition';
  import gif from '../assets/giphy.gif'
</script>
<div class="card">

<img in:fade="{{delay: 300}}" src={gif} alt="Thank you bag" />
<h2>{message}</h2>
<p>{subMessage}</p>

</div>


<style>
    .card{
    display: flex;
    flex-direction: column;
    padding: 0 1.25rem;
    justify-content: center;
    align-items: center;
  }
  img{
    width: 200px;
    height: 450px;
  }
  p{
    line-height: 1.5;
  }

  @media screen and (max-width: 420px){
    img{
      width: 150px;
      height: 350px;
    }
  }
</style>