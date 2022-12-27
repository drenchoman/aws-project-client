<script>
  import {counter} from './Stores'
  const increment = () => {
    counter.update(n => n + 1)
    
  }
import tick from '../assets/tick.svg'

</script>

<button on:click={increment}>
  Done
  <img src={tick} alt="Right Arrow"/>
</button>

<style>
  img{
    width: 30px;
  }
  button{
    display: flex;
    justify-content: center;
    align-items: center;
    max-width: fit-content;
  }
  button > * {
    margin: 0 0.5rem;
  }
</style>