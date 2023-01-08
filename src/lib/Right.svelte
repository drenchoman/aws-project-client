<script>
  import {counter} from './Stores'
  const increment = () => {
    counter.update(n => n + 1)
    
  }
  export let value
import tick from '../assets/tick.svg'

</script>

<button disabled={value.length == 0} on:click={increment}>
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
    transition: 1s ease-in-out;
  }
  button > * {
    margin: 0 0.5rem;
  }

  button:disabled{
    border: 1px solid #999999;
  background-color: #cccccc;
  color: #666666;
  }
</style>