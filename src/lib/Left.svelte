<script>
  import {counter} from './Stores'
  const decrement = () => {
    counter.update(n => n - 1)
    
  }
  import leftArrow from '../assets/left.svg'


</script>

<button on:click={decrement}>
  <img src={leftArrow} alt="Left Arrow"/>
</button>

<style>
  img{
    width: 30px;
  }
</style>