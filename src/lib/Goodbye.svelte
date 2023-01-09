<script>
  export let message
  export let subMessage
  import {onMount} from 'svelte'
  import { fade } from 'svelte/transition';
  import gif from '../assets/giphy.gif'
  import {v4 as uuidv4} from 'uuid'
  import {q1, q2, q3} from './Stores'
  const url = `http://ec2-18-234-221-144.compute-1.amazonaws.com/feedback`

  const feedback = {
        "userid": uuidv4(),
        "dateSubmitted": Date.now(),
        "q1": $q1,
        "q2": $q2.toString(),
        "q3": $q3
      }
 
  
      onMount(async () => {
    let res = await fetch(url, {
      method: 'POST',
      body: JSON.stringify(feedback),
      headers: {
        "content-type": "application/json"
      }
    })
    let json = await res.json()
    console.log(json)
  })
  
  
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